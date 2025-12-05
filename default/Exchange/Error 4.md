raised unexpected: TypeError('sequence item 0: expected str instance, int found')
Traceback (most recent call last):
  File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 451, in trace_task
    R = retval = fun(*args, **kwargs)
  File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 734, in __protected_call__
    return self.run(*args, **kwargs)
  File "/app/Exchange/tasks.py", line 13, in update_exchange_transaction_statuses
    return update()
  File "/app/Exchange/services.py", line 756, in update_exchange_transaction_statuses
    bog_response = bog_api.get_multiple_payment_status(','.join(payment_ids_by_banks['bog']))
TypeError: sequence item 0: expected str instance, int found
