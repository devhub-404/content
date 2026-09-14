# Properties e Attributes Gerenciados

`property` permite que attribute syntax chame getter/setter/deleter e mantém nome público estável. Por baixo, property é descriptor do protocol geral de attribute access.

```python
class Celsius:
    def __init__(self, value: float) -> None:
        self._value = value

    @property
    def value(self) -> float:
        return self._value
```

Use property para acesso value-like barato e previsível. Network calls, commands ou side effects grandes ficam melhores como methods.
