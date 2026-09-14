# Classes, Instances, and Attributes

A class creates a type object, and calling it normally creates an instance through `__new__` and initializes it through `__init__`. Instance attributes commonly live in an instance dictionary or slots, while methods are functions participating in descriptor binding.

```python
class Account:
    def __init__(self, owner: str) -> None:
        self.owner = owner
        self.balance = 0

    def deposit(self, amount: int) -> None:
        self.balance += amount
```

Keep object invariants behind methods and properties instead of exposing every internal detail. Python allows dynamic attributes, but explicit models are easier to type-check, test, serialize, and maintain.
