# Classes, Instances y Attributes

Una class crea un type object y llamarla normalmente crea una instance mediante `__new__` y la inicializa con `__init__`. Los instance attributes suelen vivir en dict/slots y los methods usan descriptor binding.

```python
class Account:
    def __init__(self, owner: str) -> None:
        self.owner = owner
        self.balance = 0

    def deposit(self, amount: int) -> None:
        self.balance += amount
```

Mantén invariantes detrás de methods/properties. Python permite dynamic attributes, pero modelos explícitos son más fáciles de probar, tipar y mantener.
