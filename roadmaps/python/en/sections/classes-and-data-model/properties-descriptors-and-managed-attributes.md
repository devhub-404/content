# Properties and Managed Attributes

`property` lets attribute syntax call getter, setter, and deleter logic, preserving a stable public name while implementation changes. Underneath, properties are descriptors, part of Python’s general protocol for managed attribute access.

```python
class Celsius:
    def __init__(self, value: float) -> None:
        self._value = value

    @property
    def value(self) -> float:
        return self._value
```

Use a property for value-like access that remains unsurprising and relatively cheap. Expensive network calls, commands, or operations with major side effects should usually be explicit methods instead of hidden behind attribute syntax.
