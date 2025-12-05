### Application
application_id: str
personal_id: int
status: str
	pending_deposit: "ჩარიცხვის მოლოდინში"
	successful_deposit: "წარმატებული ჩარიცხვა"
	client_clarification: "კლიენტთან დაზუსტება"
	pending_exchange: "გადარიცხვის მოლოდინში"
	pending_return: "დაბრუნების მოლოდინში"
	exchanged: "გადარიცხულია"
	returned: "დაბრუნებულია"
aml_status:
	`Null`
	pending: "მოლოდინში"
	clarification: "დაზუსტება"
	accept: "დადასტურებული"
	reject: "უარყოფილი"
create_datetime: datetime
transaction_datetime: Optional[datetime]
promised_amount: float
promised_currency: str
requested_amount: float
requested_currency: str
transferred_amount: Optional[float]
bank: str

### Transaction
transaction_id: str
personal_id: int
amount: float
currency: str
bank: str
account_number: str
status: Optional[str]
	pending _(default)_
	matched
	created_exchange
	created_surplus
	created_return

### Exchange endpoint
application_id: int - _application_id_
transaction_id: str - _transaction.transaction_id_
personal_id: int - _id_number_
account_number: str - _client_account_number_
status: str - _state_
create_datetime: datetime - _date_
transaction_datetime: Optional[datetime] - _transaction.date_
promised_amount: float - _receiver_amount_
promised_currency: str - _received_currency_
requested_amount: float - _withdrawn_amount_
requested_currency: str - _withdrawn_currency_
transferred_amount: Optional[float] - _transaction.amount_
aml_status: Optional[str] - _aml_state_
bank: str - _bank_

### F1 Update
url: [[/api/scapp-money-exchange-state-update]]
```json
[
	{
		"application_id": 12,
		"state": "successful_deposit",
		"transactions":
		[
			{
				"transaction_id": "1234",
				"create_datetime": "24/12/2024 13:45:23",
				"amount": 45.3,
				"currency": "GEL",
				"account_number": "GE36BG0000000602532568",
				"bank": "bog",
				"bank_status": "შესრულებული"
			}
		]
	}
]
```