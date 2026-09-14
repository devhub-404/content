# Type Annotations y Static Checkers

Las type annotations describen tipos pretendidos y static checkers usan esa información sin cambiar el enforcement runtime normal. Python 3.14 también cambia la evaluación de annotations en runtime.

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

count: int = 0
```

Anota primero boundaries públicas, shapes complejos y libraries reutilizables. La runtime validation sigue separada porque datos externos pueden violar una annotation.
