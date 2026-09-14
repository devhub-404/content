# Generics, Type Variables y Protocols

El typing estático expresa relaciones genéricas e interfaces estructurales con `Protocol`. Un type satisface un protocol mediante members compatibles sin herencia explícita, reflejando duck typing.

```python
from typing import Protocol, TypeVar

T = TypeVar("T")

class SizedName(Protocol):
    name: str

def first(values: list[T]) -> T:
    return values[0]
```

Usa generics cuando inputs/outputs compartan type info y protocols para pequeñas capacidades. Mantén la type machinery proporcional a la API.
