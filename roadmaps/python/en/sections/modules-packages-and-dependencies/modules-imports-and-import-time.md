# Modules, Imports, and Import Time

Each `.py` file can be a module, and importing executes its top-level code once per interpreter module cache entry before binding imported names. Packages group modules under package namespaces and may use `__init__.py` or namespace-package behavior.

```python
# pricing.py
RATE = 0.20

def total(value: float) -> float:
    return value * (1 + RATE)

# app.py
from pricing import total
```

Keep import-time work lightweight and deterministic. Opening network connections, reading large files, or starting threads during import makes testing, tooling, and application startup harder to control.
