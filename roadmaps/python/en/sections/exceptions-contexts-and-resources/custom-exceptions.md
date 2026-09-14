# Custom Exceptions

Custom exception classes give callers a stable category they can catch without parsing message text. Domain exceptions often inherit from a meaningful built-in category such as `ValueError` or directly from `Exception` when no built-in semantics fit.

```python
class InvalidOrderError(ValueError):
    pass

if total < 0:
    raise InvalidOrderError("total cannot be negative")
```

Keep exception hierarchies small and useful. Include actionable context in attributes or messages, but do not expose secrets or large payloads in logs by default.
