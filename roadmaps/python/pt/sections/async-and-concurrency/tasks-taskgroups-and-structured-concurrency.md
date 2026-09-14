# Tasks, Task Groups e Structured Concurrency

Asyncio tasks agendam coroutines concorrentemente. `TaskGroup` fornece structured concurrency: lifetime, cancellation e exceptions dos children ficam ligados ao block.

```python
async with asyncio.TaskGroup() as group:
    user_task = group.create_task(load_user())
    order_task = group.create_task(load_orders())

user = user_task.result()
orders = order_task.result()
```

Prefira ownership estruturado a fire-and-forget. Background task long-lived deve ser armazenada, monitorada e finalizada no shutdown. Estruture o lifetime das tasks para que falhas, cancelamento e cleanup tenham um owner claro.
