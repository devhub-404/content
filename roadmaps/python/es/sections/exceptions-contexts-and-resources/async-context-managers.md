# Async Context Managers

Un async context manager define `__aenter__`/`__aexit__`, permitiendo await en adquisición/cleanup. `async with` aparece en red, databases y async locks.

```python
async with session.get(url) as response:
    body = await response.text()
```

Mantén los recursos async dentro de un owner scope claro. La cancellation puede ocurrir durante cleanup, así que sigue la semántica de la library.
