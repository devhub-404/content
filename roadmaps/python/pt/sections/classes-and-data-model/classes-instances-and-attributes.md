# Classes, Instances e Attributes

Class cria type object e a chamada normalmente cria instance via `__new__` e inicializa com `__init__`. Instance attributes vivem geralmente em dict/slots e methods usam descriptor binding.

```python
class Account:
    def __init__(self, owner: str) -> None:
        self.owner = owner
        self.balance = 0

    def deposit(self, amount: int) -> None:
        self.balance += amount
```

Mantenha invariantes atrás de methods/properties. Python permite dynamic attributes, mas modelos explícitos são mais fáceis de testar, tipar e manter.
