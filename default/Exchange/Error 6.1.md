application: application_id=71237 personal_id='01017002503' account_number='False' status='pending_deposit' datetime=datetime.datetime(2025, 2, 26, 15, 38, 6) promised_amount=100.0 promised_currency='GEL' requested_amount=33.84 requested_currency='EUR' bank='bog'
[2025-02-26 11:39:45,883: WARNING/ForkPoolWorker-4] --- Logging error ---
[2025-02-26 11:39:45,883: WARNING/ForkPoolWorker-4] Traceback (most recent call last):
[2025-02-26 11:39:45,883: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/logging/__init__.py", line 1085, in emit
    msg = self.format(record)
[2025-02-26 11:39:45,883: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/logging/__init__.py", line 929, in format
    return fmt.format(record)
[2025-02-26 11:39:45,883: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/utils/log.py", line 146, in format
    msg = super().format(record)
[2025-02-26 11:39:45,884: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/logging/__init__.py", line 668, in format
    record.message = record.getMessage()
[2025-02-26 11:39:45,884: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/logging/__init__.py", line 373, in getMessage
    msg = msg % self.args
[2025-02-26 11:39:45,884: WARNING/ForkPoolWorker-4] TypeError: not all arguments converted during string formatting
[2025-02-26 11:39:45,884: WARNING/ForkPoolWorker-4] Call stack:
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/bin/celery", line 8, in <module>
    sys.exit(main())
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/__main__.py", line 15, in main
    sys.exit(_main())
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/bin/celery.py", line 217, in main
    return celery(auto_envvar_prefix="CELERY")
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/click/core.py", line 1130, in __call__
    return self.main(*args, **kwargs)
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/click/core.py", line 1055, in main
    rv = self.invoke(ctx)
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/click/core.py", line 1657, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/click/core.py", line 1404, in invoke
    return ctx.invoke(self.callback, **ctx.params)
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/click/core.py", line 760, in invoke
    return __callback(*args, **kwargs)
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/click/decorators.py", line 26, in new_func
    return f(get_current_context(), *args, **kwargs)
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/bin/base.py", line 134, in caller
    return f(ctx, *args, **kwargs)
[2025-02-26 11:39:45,885: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/bin/worker.py", line 351, in worker
    worker.start()
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/worker/worker.py", line 203, in start
    self.blueprint.start(self)
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/bootsteps.py", line 116, in start
    step.start(parent)
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/bootsteps.py", line 365, in start
    return self.obj.start()
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/concurrency/base.py", line 129, in start
    self.on_start()
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/concurrency/prefork.py", line 109, in on_start
    P = self._pool = Pool(processes=self.limit,
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/concurrency/asynpool.py", line 463, in __init__
    super().__init__(processes, *args, **kwargs)
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/pool.py", line 1046, in __init__
    self._create_worker_process(i)
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/concurrency/asynpool.py", line 480, in _create_worker_process
    return super()._create_worker_process(i)
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/pool.py", line 1158, in _create_worker_process
    w.start()
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/process.py", line 124, in start
    self._popen = self._Popen(self)
[2025-02-26 11:39:45,886: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/context.py", line 333, in _Popen
    return Popen(process_obj)
[2025-02-26 11:39:45,887: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/popen_fork.py", line 24, in __init__
    self._launch(process_obj)
[2025-02-26 11:39:45,887: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/popen_fork.py", line 79, in _launch
    code = process_obj._bootstrap()
[2025-02-26 11:39:45,887: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/process.py", line 327, in _bootstrap
    self.run()
[2025-02-26 11:39:45,887: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/process.py", line 114, in run
    self._target(*self._args, **self._kwargs)
[2025-02-26 11:39:45,887: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/pool.py", line 292, in __call__
    sys.exit(self.workloop(pid=pid))
[2025-02-26 11:39:45,887: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/billiard/pool.py", line 362, in workloop
    result = (True, prepare_result(fun(*args, **kwargs)))
[2025-02-26 11:39:45,887: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 649, in fast_trace_task
    R, I, T, Rstr = tasks[task].__trace__(
[2025-02-26 11:39:45,888: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 451, in trace_task
    R = retval = fun(*args, **kwargs)
[2025-02-26 11:39:45,888: WARNING/ForkPoolWorker-4]   File "/usr/local/lib/python3.8/site-packages/celery/app/trace.py", line 734, in __protected_call__
    return self.run(*args, **kwargs)
[2025-02-26 11:39:45,888: WARNING/ForkPoolWorker-4]   File "/app/Exchange/tasks.py", line 10, in process_exchange_transactions
    return process(db)
[2025-02-26 11:39:45,888: WARNING/ForkPoolWorker-4]   File "/app/Exchange/services.py", line 1075, in process_exchange_transactions
    application_responses, pseudo_application_responses_sent = match_grouped_transactions_and_applications(
[2025-02-26 11:39:45,888: WARNING/ForkPoolWorker-4]   File "/app/Exchange/services.py", line 860, in match_grouped_transactions_and_applications
    logger.info(
[2025-02-26 11:39:45,888: WARNING/ForkPoolWorker-4] Message: '\x1b[37;1mupdated grouped transaction:'
Arguments: ("\x1b[0;37mamount=100.0 currency='GEL' source_account_number='GE60BG0000000611236500' personal_id='01017002503' requested_amount=33.84 requested_currency='EUR' application_id=71237 bank='bog' status='matched' first_transaction_datetime=datetime.datetime(2025, 2, 26, 15, 39, 45, 669132) last_transaction_datetime=datetime.datetime(2025, 2, 26, 15, 39, 45, 669132) id=84\x1b[0m",)