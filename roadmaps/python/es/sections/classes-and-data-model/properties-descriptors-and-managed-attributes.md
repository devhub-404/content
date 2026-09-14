# Properties y Attributes Gestionados

`property` permite que attribute syntax llame getter/setter/deleter y mantiene un nombre público estable. Por debajo, property es un descriptor del protocol general de attribute access.

```python
class Celsius:
    def __init__(self, value: float) -> None:
        self._value = value

    @property
    def value(self) -> float:
        return self._value
```

Usa property para acceso value-like barato y predecible. Network calls, commands o side effects grandes son mejores como methods.
