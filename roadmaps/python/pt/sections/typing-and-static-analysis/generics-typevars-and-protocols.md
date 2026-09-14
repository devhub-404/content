# Generics, Type Variables e Protocols

Typing estático expressa relações genéricas e interfaces estruturais com `Protocol`. Um type satisfaz protocol por members compatíveis sem inheritance explícita, refletindo duck typing.

```python
from typing import Protocol, TypeVar

T = TypeVar("T")

class SizedName(Protocol):
    name: str

def first(values: list[T]) -> T:
    return values[0]
```

Use generics quando inputs/outputs compartilham type info e protocols para pequenas capacidades. Mantenha type machinery proporcional à API.
