# `async`, `await` y Coroutines

Una `async def` retorna un coroutine object que se ejecuta cuando se await/schedule. `await` suspende la coroutine y permite al event loop ejecutar otras tasks durante I/O.

```python
async def load(url: str) -> bytes:
    response = await fetch(url)
    return response.body
```

Asyncio es excelente para I/O concurrente con APIs nonblocking, no para acelerar trabajo CPU-heavy por sí solo. Evita blocking calls en el event-loop thread.
