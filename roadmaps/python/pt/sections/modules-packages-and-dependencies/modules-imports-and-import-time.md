# Modules, Imports e Import Time

Cada `.py` pode ser module e import executa top-level code uma vez por entry no module cache. Packages agrupam modules e podem usar `__init__.py` ou namespace packages.

```python
# pricing.py
RATE = 0.20

def total(value: float) -> float:
    return value * (1 + RATE)

# app.py
from pricing import total
```

Mantenha import-time work leve e determinístico. Network, files grandes ou threads no import dificultam testes e startup.
