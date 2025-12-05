```bash
--- Logging error ---
Traceback (most recent call last):
  File "/usr/lib/python3.10/logging/__init__.py", line 1100, in emit
    msg = self.format(record)
  File "/usr/lib/python3.10/logging/__init__.py", line 943, in format
    return fmt.format(record)
  File "/usr/lib/python3.10/logging/__init__.py", line 678, in format
    record.message = record.getMessage()
  File "/usr/lib/python3.10/logging/__init__.py", line 368, in getMessage
    msg = msg % self.args
TypeError: not all arguments converted during string formatting
Call stack:
  File "/usr/local/bin/uvicorn", line 8, in <module>
    sys.exit(main())
  File "/usr/local/lib/python3.10/dist-packages/click/core.py", line 1130, in __call__
    return self.main(*args, **kwargs)
  File "/usr/local/lib/python3.10/dist-packages/click/core.py", line 1055, in main
    rv = self.invoke(ctx)
  File "/usr/local/lib/python3.10/dist-packages/click/core.py", line 1404, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/usr/local/lib/python3.10/dist-packages/click/core.py", line 760, in invoke
    return __callback(*args, **kwargs)
  File "/usr/local/lib/python3.10/dist-packages/uvicorn/main.py", line 403, in main
    run(
  File "/usr/local/lib/python3.10/dist-packages/uvicorn/main.py", line 568, in run
    server.run()
  File "/usr/local/lib/python3.10/dist-packages/uvicorn/server.py", line 59, in run
    return asyncio.run(self.serve(sockets=sockets))
  File "/usr/lib/python3.10/asyncio/runners.py", line 44, in run
    return loop.run_until_complete(main)
  File "/usr/lib/python3.10/asyncio/base_events.py", line 636, in run_until_complete
    self.run_forever()
  File "/usr/lib/python3.10/asyncio/base_events.py", line 603, in run_forever
    self._run_once()
  File "/usr/lib/python3.10/asyncio/base_events.py", line 1909, in _run_once
    handle._run()
  File "/usr/lib/python3.10/asyncio/events.py", line 80, in _run
    self._context.run(self._callback, *self._args)
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/base.py", line 70, in coro
    await self.app(scope, receive_or_disconnect, send_no_error)
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py", line 68, in __call__
    await self.app(scope, receive, sender)
  File "/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py", line 18, in __call__
    await self.app(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/routing.py", line 718, in __call__
    await route.handle(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/routing.py", line 276, in handle
    await self.app(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/routing.py", line 66, in app
    response = await func(request)
  File "/usr/local/lib/python3.10/dist-packages/fastapi/routing.py", line 237, in app
    raw_response = await run_endpoint_function(
  File "/usr/local/lib/python3.10/dist-packages/fastapi/routing.py", line 163, in run_endpoint_function
    return await dependant.call(**values)
  File "/app/Exchange/router.py", line 20, in exchange_or_return
    return services.exchange_or_return(application=payload, db=db)
  File "/app/Exchange/services.py", line 354, in exchange_or_return
    sent_transaction = send_exchange(
  File "/app/Exchange/services.py", line 276, in send_exchange
    sent_transaction = return_to_sender(
  File "/app/Exchange/services.py", line 505, in return_to_sender
    logger.info(
  File "/app/logger_conf.py", line 155, in info
    return self.logger.info(formatted_msg, *args, **kwargs)
Message: "\x1b[31;1mcouldn't be returned \x1b[0;37m<class 'Exchange.schemas.GroupedExchangeTransaction'>"
Arguments: ('\x1b[31;1because the sent transaction already existed\x1b[0m',)
INFO:     192.168.2.110:48066 - "POST /exchange_or_return HTTP/1.1" 500 Internal Server Error
ERROR:    Exception in ASGI application
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/anyio/streams/memory.py", line 94, in receive
    return self.receive_nowait()
  File "/usr/local/lib/python3.10/dist-packages/anyio/streams/memory.py", line 89, in receive_nowait
    raise WouldBlock
anyio.WouldBlock

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/base.py", line 78, in call_next
    message = await recv_stream.receive()
  File "/usr/local/lib/python3.10/dist-packages/anyio/streams/memory.py", line 114, in receive
    raise EndOfStream
anyio.EndOfStream

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/uvicorn/protocols/http/h11_impl.py", line 429, in run_asgi
    result = await app(  # type: ignore[func-returns-value]
  File "/usr/local/lib/python3.10/dist-packages/uvicorn/middleware/proxy_headers.py", line 78, in __call__
    return await self.app(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/fastapi/applications.py", line 276, in __call__
    await super().__call__(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/applications.py", line 122, in __call__
    await self.middleware_stack(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py", line 184, in __call__
    raise exc
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/errors.py", line 162, in __call__
    await self.app(scope, receive, _send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/base.py", line 108, in __call__
    response = await self.dispatch_func(request, call_next)
  File "/usr/local/lib/python3.10/dist-packages/fastapi_sqlalchemy/middleware.py", line 44, in dispatch
    response = await call_next(request)
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/base.py", line 84, in call_next
    raise app_exc
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/base.py", line 70, in coro
    await self.app(scope, receive_or_disconnect, send_no_error)
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py", line 79, in __call__
    raise exc
  File "/usr/local/lib/python3.10/dist-packages/starlette/middleware/exceptions.py", line 68, in __call__
    await self.app(scope, receive, sender)
  File "/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py", line 21, in __call__
    raise e
  File "/usr/local/lib/python3.10/dist-packages/fastapi/middleware/asyncexitstack.py", line 18, in __call__
    await self.app(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/routing.py", line 718, in __call__
    await route.handle(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/routing.py", line 276, in handle
    await self.app(scope, receive, send)
  File "/usr/local/lib/python3.10/dist-packages/starlette/routing.py", line 66, in app
    response = await func(request)
  File "/usr/local/lib/python3.10/dist-packages/fastapi/routing.py", line 237, in app
    raw_response = await run_endpoint_function(
  File "/usr/local/lib/python3.10/dist-packages/fastapi/routing.py", line 163, in run_endpoint_function
    return await dependant.call(**values)
  File "/app/Exchange/router.py", line 20, in exchange_or_return
    return services.exchange_or_return(application=payload, db=db)
  File "/app/Exchange/services.py", line 354, in exchange_or_return
    sent_transaction = send_exchange(
  File "/app/Exchange/services.py", line 281, in send_exchange
    sent_transaction.details = f'Result code: {error_code}' + f' message: {error_message}' if error_message is not None else ''

```