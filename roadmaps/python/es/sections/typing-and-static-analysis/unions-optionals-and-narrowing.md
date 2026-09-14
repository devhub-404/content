# Unions, Optionals y Narrowing

Union `A | B` expresa alternativas y `T | None` un valor opcional. Los checkers hacen narrowing mediante `is None`, `isinstance`, pattern matching y type guards.

```python
def length(value: str | None) -> int:
    if value is None:
        return 0
    return len(value)
```

Modela ausencia legítima explícitamente en vez de usar `Any`. Haz narrowing con checks que representen la regla de runtime.
