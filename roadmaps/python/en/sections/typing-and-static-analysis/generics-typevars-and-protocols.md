# Generics, Type Variables, and Protocols

Static typing can express generic relationships with type parameters/variables and structural interfaces with `Protocol`. A protocol lets a type satisfy an interface through compatible members without explicit inheritance, similar to Python’s runtime duck typing.

```python
from typing import Protocol, TypeVar

T = TypeVar("T")

class SizedName(Protocol):
    name: str

def first(values: list[T]) -> T:
    return values[0]
```

Use generics when inputs and outputs share type information, and protocols when callers need a small capability rather than a concrete class hierarchy. Keep advanced type-level machinery proportionate to the API’s actual complexity.
