# Numbers, Booleans, and `None`

Python has arbitrary-precision integers, floating-point numbers, complex numbers, booleans, and the singleton `None` for absence or no meaningful result. `bool` is a subclass of `int`, although application code should generally treat Boolean state semantically rather than numerically.

```python
count = 42
ratio = 0.75
price = 19.99
ready = True
missing = None
```

Binary floating-point cannot represent every decimal fraction exactly. Use `decimal.Decimal` where exact decimal arithmetic and explicit rounding rules are part of the domain, and `fractions.Fraction` when rational arithmetic is a better fit.
