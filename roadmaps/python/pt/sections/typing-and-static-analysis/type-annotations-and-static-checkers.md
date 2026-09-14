# Type Annotations e Static Checkers

Type annotations descrevem tipos pretendidos e static checkers usam essa informação sem mudar enforcement runtime comum. Python 3.14 também altera evaluation de annotations em runtime.

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

count: int = 0
```

Anote boundaries públicas, shapes complexos e libraries reutilizáveis primeiro. Runtime validation continua separada porque dados externos podem violar annotation.
