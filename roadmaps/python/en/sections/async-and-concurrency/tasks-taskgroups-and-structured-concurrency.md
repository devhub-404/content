# Tasks, Task Groups, and Structured Concurrency

Asyncio tasks schedule coroutines concurrently. `TaskGroup` gives structured concurrency: child task lifetime, cancellation, and exception aggregation are tied to the enclosing block rather than becoming detached background work.

```python
async with asyncio.TaskGroup() as group:
    user_task = group.create_task(load_user())
    order_task = group.create_task(load_orders())

user = user_task.result()
orders = order_task.result()
```

Prefer structured task ownership over fire-and-forget tasks. If a background task is truly process-long-lived, store it, monitor failures, and define how application shutdown cancels and awaits it.
