# Modules, Imports e Import Time

Cada `.py` puede ser module e import ejecuta top-level code una vez por entry en el module cache. Los packages agrupan modules y pueden usar `__init__.py` o namespace packages.

```python
# pricing.py
RATE = 0.20

def total(value: float) -> float:
    return value * (1 + RATE)

# app.py
from pricing import total
```

Mantén el import-time work ligero y determinista. Red, files grandes o threads durante import dificultan tests y startup.
