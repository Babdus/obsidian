received_grouped_transaction: amount=1.16 currency='GEL' source_account_number='GE47BG0000000345911373' personal_id='19001084697' requested_amount=0.36 requested_currency='USD' application_id=778 bank='bog' status='matched' first_transaction_datetime=datetime.datetime(2025, 1, 17, 11, 23, 2, 758637) last_transaction_datetime=datetime.datetime(2025, 1, 17, 11, 23, 2, 758637) id=33
INFO:     192.168.8.150:47690 - "POST /exchange_or_return HTTP/1.1" 500 Internal Server Error
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
    await self.app(scope, receive, send)
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
    return await dependant.call(\*\*values)
  File "/app/Exchange/router.py", line 19, in exchange_or_return
    return services.exchange_or_return(application=payload)
  File "/app/Exchange/services.py", line 166, in exchange_or_return
    transfer_transaction_to_banks(
  File "/app/Exchange/services.py", line 95, in transfer_transaction_to_banks
    DomesticTransactionBog(
  File "pydantic/main.py", line 341, in pydantic.main.BaseModel.__init__
pydantic.error_wrappers.ValidationError: 4 validation errors for DomesticTransactionBog
DispatchType
  field required (type=value_error.missing)
Amount
  field required (type=value_error.missing)
DocumentNo
  field required (type=value_error.missing)
BeneficiaryAccountNumber
  field required (type=value_error.missing)

# 2

pydantic.error_wrappers.ValidationError: 4 validation errors for ForeignTransactionBog
Amount
  field required (type=value_error.missing)
Currency
  field required (type=value_error.missing)
DocumentNo
  field required (type=value_error.missing)
BeneficiaryAccountNumber
  field required (type=value_error.missing)