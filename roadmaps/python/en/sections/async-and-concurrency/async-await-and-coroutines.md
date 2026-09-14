# `async`, `await`, and Coroutines

An `async def` call returns a coroutine object; it executes when awaited or scheduled by an event loop. `await` suspends the current coroutine until an awaitable progresses, letting the event loop run other tasks instead of blocking on asynchronous I/O.

```python
async def load(url: str) -> bytes:
    response = await fetch(url)
    return response.body
```

Asyncio is best for high-concurrency I/O where libraries expose nonblocking APIs. It does not make CPU-heavy Python code faster by itself. Avoid calling blocking file/network/database APIs directly on the event-loop thread.
