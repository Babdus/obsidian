```bash
Sending payload [{'Nomination': 'არასწორი თანხის უკან დაბრუნება', 'PayerInn': '205274273', 'PayerName': 'მიკროსაფინანსო ორგანიზაცია სვის კაპიტალი', 'DispatchType': 'MT103', 'ValueDate': '2025-04-28T08:25:04.640863+04:00', 'IsSalary': False, 'UniqueId': '63e345ea-63e4-4236-82a0-fec6ad25f940', 'Amount': 1.1, 'DocumentNo': '63e345ea-63e4-4236-82a0-fec6ad25f940', 'SourceAccountNumber': 'GE17BG0000000607535657', 'BeneficiaryAccountNumber': 'GE47BG0000000345911373', 'BeneficiaryBankCode': 'BAGAGE22', 'BeneficiaryInn': '19001084697', 'CheckInn': 'true', 'BeneficiaryName': 'client_name', 'AdditionalInformation': None}] to https://api.businessonline.ge/api/documents/domestic
[2025-04-28 08:25:04,939: ERROR/ForkPoolWorker-1] Task Web_Exchange.tasks.process_exchange_transactions[51eeed05-5291-452d-a6ac-6d01794d1650] raised unexpected: HTTPException(status_code=500, detail='ტრანზაქცია ვერ შესრულდა!')
Traceback (most recent call last):
  File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 451, in trace_task
    R = retval = fun(*args, **kwargs)
  File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 734, in __protected_call__
    return self.run(*args, **kwargs)
  File "/app/Web_Exchange/tasks.py", line 10, in process_exchange_transactions
    return process(db)
  File "/app/Web_Exchange/services.py", line 572, in process_exchange_transactions
    transaction_pairs = return_to_senders(db, invalid_transactions)
  File "/app/Web_Exchange/services.py", line 434, in return_to_senders
    saved_transaction = return_to_sender(db, received_transaction)
  File "/app/Web_Exchange/services.py", line 388, in return_to_sender
    response = post_transaction_in_banks(
  File "/app/Web_Exchange/services.py", line 278, in post_transaction_in_banks
    response = bog_api.create_transaction_domestic_currency(
  File "/app/Bog_API/bog_api.py", line 237, in create_transaction_domestic_currency
    raise HTTPException(response.status_code, detail="ტრანზაქცია ვერ შესრულდა!")
fastapi.exceptions.HTTPException: 500
```
