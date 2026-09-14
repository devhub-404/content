# Context Managers and `with`

A context manager defines entry and exit behavior through `__enter__`/`__exit__` or helper utilities such as `contextlib.contextmanager`. The `with` statement guarantees exit logic runs even when the body raises an exception.

```python
with open(path, "r", encoding="utf-8") as file:
    text = file.read()
```

Use context managers for files, locks, transactions, temporary state, tracing spans, and other scoped lifetimes. They communicate ownership and cleanup more clearly than paired open/close calls separated across control-flow paths.
