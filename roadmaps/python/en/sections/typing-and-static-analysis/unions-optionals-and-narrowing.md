# Unions, Optionals, and Narrowing

Union syntax `A | B` expresses alternatives and `T | None` an optional value. Static checkers narrow unions through `is None`, `isinstance`, pattern matching, user-defined type guards, and other control-flow evidence.

```python
def length(value: str | None) -> int:
    if value is None:
        return 0
    return len(value)
```

Model legitimate absence explicitly instead of using a broad `Any`. Narrow with checks that match the runtime domain rule; a type checker is strongest when the code already distinguishes states clearly.
