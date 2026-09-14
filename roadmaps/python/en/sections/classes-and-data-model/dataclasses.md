# Dataclasses

`dataclasses.dataclass` generates common methods such as `__init__`, `__repr__`, and equality from annotated fields. Options control ordering, immutability-like behavior, keyword-only fields, slots, and other generated details.

```python
from dataclasses import dataclass

@dataclass(frozen=True, slots=True)
class User:
    id: int
    name: str
```

A frozen dataclass prevents ordinary field assignment but does not deeply freeze mutable values stored inside it. Use dataclasses for data-oriented types; use a normal class when initialization, invariants, or behavior dominate the design.
