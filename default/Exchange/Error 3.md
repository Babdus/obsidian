sqlalchemy.exc.TimeoutError: QueuePool limit of size 5 overflow 10 reached, connection timed out, timeout 30.00 (Background on this error at: https://sqlalche.me/e/20/3o7r)


File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 451, in trace_task
    R = retval = fun(*args, **kwargs)
  File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 734, in __protected_call__
    return self.run(*args, **kwargs)
  File "/app/Exchange/tasks.py", line 7, in process_exchange_transactions
    return process()
  File "/app/Exchange/services.py", line 698, in process_exchange_transactions
    new_transactions = filter_only_new_transactions(db, merged_transactions)
  File "/app/Exchange/services.py", line 339, in filter_only_new_transactions
    existing_transactions = db.query(models.ExchangeTransaction.transaction_id).filter(
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/orm/query.py", line 2697, in all
    return self._iter().all()  # type: ignore
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/orm/query.py", line 2855, in _iter
    result: Union[ScalarResult[_T], Result[_T]] = self.session.execute(
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/orm/session.py", line 2229, in execute
    return self._execute_internal(
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/orm/session.py", line 2114, in _execute_internal
    conn = self._connection_for_bind(bind)
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/orm/session.py", line 1981, in _connection_for_bind
    return trans._connection_for_bind(engine, execution_options)
  File "<string>", line 2, in _connection_for_bind
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/orm/state_changes.py", line 137, in _go
    ret_value = fn(self, *arg, **kw)
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/orm/session.py", line 1108, in _connection_for_bind
    conn = bind.connect()
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/engine/base.py", line 3251, in connect
    return self._connection_cls(self)
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/engine/base.py", line 145, in __init__
    self._dbapi_connection = engine.raw_connection()
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/engine/base.py", line 3275, in raw_connection
    return self.pool.connect()
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/pool/base.py", line 455, in connect
    return _ConnectionFairy._checkout(self)
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/pool/base.py", line 1271, in _checkout
    fairy = _ConnectionRecord.checkout(pool)
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/pool/base.py", line 719, in checkout
    rec = pool._do_get()
  File "/usr/local/lib/python3.8/site-packages/sqlalchemy/pool/impl.py", line 157, in _do_get
    raise exc.TimeoutError(
sqlalchemy.exc.TimeoutError: QueuePool limit of size 5 overflow 10 reached, connection timed out, timeout 30.00 (Background on this error at: https://sqlalche.me/e/20/3o7r)
