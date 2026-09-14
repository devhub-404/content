# Números, Booleanos e `None`

Python possui integers de precisão arbitrária, floating point, complex, bool e singleton `None` para ausência. `bool` é subclass de `int`, embora código de aplicação normalmente trate boolean semanticamente.

```python
count = 42
ratio = 0.75
price = 19.99
ready = True
missing = None
```

Floating point binário não representa toda fração decimal. Use `decimal.Decimal` para aritmética decimal exata e rounding explícito, e `Fraction` quando racional é adequado.
