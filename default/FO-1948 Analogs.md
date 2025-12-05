###### Code
```python
def find_same_analogs(self):  
    self.ensure_one()  
    fuel_type = []  
    if self.fuel_type.id == self.env['sw.vehicle.fuel.type'].search([('name', '=', 'ბენზინი/გაზი')]).id:  
        fuel_type.append(self.fuel_type.id)  
        fuel_type.append(self.env['sw.vehicle.fuel.type'].search([('name', '=', 'ბენზინი')]).id)  
    elif self.fuel_type.id == self.env['sw.vehicle.fuel.type'].search([('name', '=', 'ჰიბრიდი-აირი')]).id:  
        fuel_type.append(self.fuel_type.id)  
        fuel_type.append(self.env['sw.vehicle.fuel.type'].search([('name', '=', 'ჰიბრიდი')]).id)  
    else:  
        fuel_type.append(self.fuel_type.id)  
    find_compartment = self.env.context.get('find_compartment')
    
query = f"""
    select sptv.id
    from sw_project_task_vehicle sptv
    left join sw_vehicle sv on sptv.vehicle_id = sv.id
    where sv.manufacturer = {self.manufacturer.id} and
	    sv.model = {self.model.id} and
	    sv.year = '{self.year}' and
        sv.fuel_type in ({str(fuel_type)[1:-1]}) and
	    sv.engine_volume >= {self.engine_volume - 35} and
	    sv.engine_volume <= {self.engine_volume + 35} and
	    sv.st_wheel_position = '{self.st_wheel_position}'
	    {'and sptv.compartment is true' if find_compartment ==1 else 'and (sptv.compartment is null or sptv.compartment is false)'}
    order by sptv.id desc
    LIMIT 300
    """    # დალიმიტდა რამდენი ერთნაირი ავტომობილი წამოიღოს  
    self.env.cr.execute(query)  
    same_vehicle_ids = [f[0] for f in self.env.cr.fetchall()]  
    same_vehicle = self.env['sw.project.task.vehicle'].browse(same_vehicle_ids)  
    analog_duration = self.env.ref('swiss_capital_base.sw_config_parameter_analog_duration').value or 90  
    today_start = datetime.datetime.now().replace(hour=0, minute=0, second=0, microsecond=0) - datetime.timedelta(days=int(analog_duration))  
    analogs = same_vehicle.mapped('analog_ids').filtered(lambda analog: fields.Datetime.from_string(analog.create_date) > today_start)  
    if analogs:  
        val_list = []  
        veh_id = None  
        for analog in analogs:  
            if veh_id is None or veh_id == analog.task_vehicle_id.id:  
                veh_id = analog.task_vehicle_id.id  
                analog_vals = {  
                    'name': analog.name,  
                    'realization_price': analog.realization_price,  
                    'image': analog.image,  
                }  
                val_list.append((0, 0, analog_vals))  
        for t in val_list:  
            _logger.info(t)  
  
        self.analog_ids.unlink()  
        self.analog_ids = list(reversed(val_list))  
    else:  
        raise UserError("ანალოგები ვერ იპოვა!")  
    return {'type': 'ir.actions.do_nothing'}
```
###### Suggestions

1. Why not
   ```python
   self.fuel_type.name == 'ბენზინი/გაზი'
   ```
   instead of
   ```python
   self.fuel_type.id == self.env['sw.vehicle.fuel.type'].search([('name', '=', 'ბენზინი/გაზი')]).id
   ```
   ?
   
2. Why not
   ```python
   self.fuel_type.name == 'ჰიბრიდი-აირი'
   ```
   instead of
   ```python
   self.fuel_type.id == self.env['sw.vehicle.fuel.type'].search([('name', '=', 'ჰიბრიდი-აირი')]).id
   ```
   ?
   
## Testing SQL

```sql
SELECT
	v.id v_id,
	vin,
	ptv.id ptv_id,
	pt.name project_task_name,
	analog.id analog_id,
	analog.create_date create_date,
	year,
	manufacturer.name manufacturer,
	model.name model,
	fuel.name fuel_type,
	engine_volume,
	st_wheel_position
FROM sw_vehicle v
	JOIN sw_vehicle_fuel_type fuel
		ON fuel.id = v.fuel_type
	JOIN sw_vehicle_manufacturer manufacturer
		ON manufacturer.id = v.manufacturer
	JOIN sw_vehicle_model model
		ON model.id = v.model
	LEFT OUTER JOIN sw_project_task_vehicle ptv
		ON ptv.vehicle_id = v.id
	JOIN project_task pt
		ON ptv.task_id = pt.id
	LEFT OUTER JOIN sw_analog analog
		ON analog.task_vehicle_id = ptv.id
WHERE vin IN ('5TDBT44A44S209142', '5UXZW0C59CL672055');
```