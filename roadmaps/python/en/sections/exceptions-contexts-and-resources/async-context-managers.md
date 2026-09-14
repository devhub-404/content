# Async Context Managers

An asynchronous context manager defines `__aenter__` and `__aexit__`, allowing resource acquisition or cleanup to await. `async with` is common for network sessions, async database transactions, and locks supplied by asynchronous libraries.

```python
async with session.get(url) as response:
    body = await response.text()
```

Keep async resources inside a clear owner scope just as with synchronous resources. Cancellation can occur during async cleanup, so libraries often define careful shutdown semantics that callers should follow rather than abandoning tasks.
