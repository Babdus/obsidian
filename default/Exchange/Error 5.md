raised unexpected: KeyError('transactionType')
Traceback (most recent call last):
  File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 451, in trace_task
    R = retval = fun(*args, \*\*kwargs)
  File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 734, in \_\_protected_call\_\_
    return self.run(*args, \*\*kwargs)
  File "/app/Exchange/tasks.py", line 8, in process_exchange_transactions
    return process()
  File "/app/Exchange/services.py", line 751, in process_exchange_transactions
    filtered_pending_grouped_transactions = return_to_sender_expired_grouped_transactions(
  File "/app/Exchange/services.py", line 702, in return_to_sender_expired_grouped_transactions
    return_to_sender(db, updated_grouped_transaction)
  File "/app/Exchange/services.py", line 340, in return_to_sender
    if not can_be_returned(grouped_transaction):
  File "/app/Exchange/services.py", line 323, in can_be_returned
    sent_transactions = get_sent_transactions_from_tbc()
  File "/app/Exchange/services.py", line 300, in get_sent_transactions_from_tbc
    if str(transaction['transactionType']) == '30':
KeyError: 'transactionType'