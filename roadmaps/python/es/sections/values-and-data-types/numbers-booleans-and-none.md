# Números, Booleanos y `None`

Python tiene integers de precisión arbitraria, floating point, complex, bool y el singleton `None` para ausencia. `bool` es subclass de `int`, aunque el código de aplicación suele tratar Boolean semánticamente.

```python
count = 42
ratio = 0.75
price = 19.99
ready = True
missing = None
```

El floating point binario no representa toda fracción decimal. Usa `decimal.Decimal` para aritmética decimal exacta y rounding explícito, y `Fraction` cuando lo racional encaje.
