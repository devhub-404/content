# Timeouts, Cancellation, and Backpressure

Async cancellation is cooperative and typically delivered through `CancelledError` at suspension points. Timeouts impose cancellation scopes, while bounded queues and semaphores provide backpressure and capacity control.

```python
async with asyncio.timeout(5):
    result = await service.load()

queue = asyncio.Queue(maxsize=100)
```

Do not swallow cancellation accidentally in broad exception handling. Limit concurrency around scarce resources instead of creating unbounded tasks, and define which layer owns retries and timeout budgets.
