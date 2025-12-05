[[TBC password changer]]
[[Exchange data]]
#### odoo venv
```bash
cd /home/tato/Desktop/odoo11/odoo
deactivate
source /home/tato/Desktop/swiss_odoo/venv/bin/activate
```
#### odoo shell
```bash
./odoo-bin shell -c odoo.conf -d Swissdb --addons path=addons,swisscapital
```

#### Docker db
```
docker exec -it swissCap__postgresql bash
psql -h localhost -U postgres
```
## Servers
#### prod servers
###### f1: 110
```bash
ssh logreader@192.168.2.110
XH2h7M0T68WVI4413
```
###### bank APIs
```bash
ssh bank@192.168.2.119
4QDYA2BKeK475EcCXy7
```
#### test servers
###### f1: 150
```bash
ssh root@192.168.8.150
Cd348adm1995bf010

ssh root@192.168.8.190
bst2020#

ssh root@192.168.8.191
bst2020#
```
###### f1: 160
```bash
ssh root@192.168.8.160
bst2020#
```
###### f1: 105
```bash
ssh root@192.168.8.105
	ym5qJy9SBR3CMAd
```
###### bank APIs
```bash
ssh bank@192.168.8.116
ZvTPgGerepOnWjT
``` 
###### Report
```bash
ssh root@192.168.8.114
SSdN1991
```
## DBs
#### prod DBs
###### f1

```
192.168.2.106:5432 
Database: SwissCapital  
User: prodreadonly  
Pass: 2YFves7sV3T8itE3d
```
#### test DBs
###### f1: 150
```
192.168.8.149:5432
postgres
bst2020#
```
###### f1: 160
```
192.168.8.152:5432
postgres
Bcqk821Ncb162O882XcECKAW
```
#### ChatGPT
```
User - ai_team@swisscapital.ge  
Pass - m7G-tt5HH*gwDk
```
#### connections
###### qisa cursor
```python
with self.env['swiss.database.connections'].with_context({'database': 'qisa'}) as cursor:
```
###### abacus cursor
```python
with self.env['swiss.database.connections'].with_context({'database': 'abacus'}) as cursor:
```

```python
with SWDatabaseConnection.with_context({'database': 'abacus'}) as cursor:
```
###### report server cursor
```python
with self.env['swiss.database.connections'].with_context({'database': 'report'}) as cursor:
```
###### aml cursor
```python
with self.env['swiss.database.connections'].with_context({'database': 'aml'}) as cursor:
```
###### f1 cursor
```python
with self.env['swiss.database.connections'].with_context({'database': 'f1'}) as cursor:
```
###### bi cursor
```python
with self.env['swiss.database.connections'].with_context({'database': 'bi'}) as cursor:
```
###### direx cursor
```python
with self.env['swiss.database.connections'].with_context({'database': 'direx'}) as cursor:
```