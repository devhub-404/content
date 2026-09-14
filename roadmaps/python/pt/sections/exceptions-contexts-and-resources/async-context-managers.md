# Async Context Managers

Async context manager define `__aenter__`/`__aexit__`, permitindo await em aquisição/cleanup. `async with` aparece em network, databases e async locks.

```python
async with session.get(url) as response:
    body = await response.text()
```

Mantenha recursos async dentro de owner scope claro. Cancellation pode acontecer durante cleanup, então siga semântica da library. Esse padrão deixa aquisição e cleanup no mesmo fluxo e reduz caminhos em que um recurso pode permanecer aberto.
