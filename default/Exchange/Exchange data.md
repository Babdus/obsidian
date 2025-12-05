## APIs
#### TBC
[TBC API](https://developers.tbcbank.ge/docs/checkout-api-overview)
###### Example payload
```json
{
  "partner_account_number": "GE59TB0653245064300001",
  "sc_account_number": "GE55TB7630836020100030",
  "currency_code": "USD",
  "amount": 1.0,
  "currency": "USD",
  "additional_description": "string",
  "description": "სესხის თანხა",
  "beneficiary_name": "გივი მურვანიძე",
  "beneficiary_tax_code": "01017002503"
}
```
#### BOG
[BOG API](https://api.bog.ge/docs/en/)
###### Domestic transfer example result
```json
{
  "status_code": 200,
  "TransferID": 118479954,
  "ResultCode": 0
}
```

## Data
#### Swisscapital
###### BOG account number
GE36BG0000000602544568
###### TBC account number
GE55TB7630836020100030
#### Givi
###### ID number
01017002503
###### BOG account number
GE60BG0000000611236500
###### TBC account number
GE59TB0653245064300001