# Context Managers y `with`

Un context manager define entry/exit mediante protocol o `contextlib`, y `with` garantiza exit incluso con exception.

```python
with open(path, "r", encoding="utf-8") as file:
    text = file.read()
```

Úsalo para files, locks, transactions, temporary state, tracing y lifetimes scoped. Comunica ownership/cleanup mejor que open/close separados. Este patrón mantiene adquisición y cleanup en el mismo flujo y reduce rutas donde un recurso puede quedar abierto.
