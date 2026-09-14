# `async`, `await` e Coroutines

`async def` retorna coroutine object que executa quando awaited/scheduled. `await` suspende a coroutine e permite ao event loop rodar outras tasks durante I/O.

```python
async def load(url: str) -> bytes:
    response = await fetch(url)
    return response.body
```

Asyncio é ótimo para I/O concorrente com APIs nonblocking, não para acelerar CPU-heavy work sozinho. Evite blocking calls no event-loop thread.
