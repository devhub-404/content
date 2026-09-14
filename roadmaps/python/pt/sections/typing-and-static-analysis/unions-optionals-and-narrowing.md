# Unions, Optionals e Narrowing

Union `A | B` expressa alternativas e `T | None` valor opcional. Checkers fazem narrowing por `is None`, `isinstance`, pattern matching e type guards.

```python
def length(value: str | None) -> int:
    if value is None:
        return 0
    return len(value)
```

Modele ausência legítima explicitamente em vez de `Any`. Faça narrowing com checks que representam a regra de runtime. O objetivo é representar estados válidos com precisão, sem transformar cada detalhe de runtime em uma annotation complexa.
