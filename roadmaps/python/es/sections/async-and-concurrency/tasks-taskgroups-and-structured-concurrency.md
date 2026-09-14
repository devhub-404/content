# Tasks, Task Groups y Structured Concurrency

Las asyncio tasks programan coroutines concurrentemente. `TaskGroup` ofrece structured concurrency: lifetime, cancellation y exceptions de los children quedan ligados al block.

```python
async with asyncio.TaskGroup() as group:
    user_task = group.create_task(load_user())
    order_task = group.create_task(load_orders())

user = user_task.result()
orders = order_task.result()
```

Prefiere ownership estructurado frente a fire-and-forget. Una background task long-lived debe almacenarse, monitorizarse y cerrarse durante shutdown. Estructura el lifetime de las tasks para que fallos, cancelación y cleanup tengan un owner claro.
