# Dataclasses

`dataclass` genera `__init__`, `__repr__`, equality y otros desde fields anotados. Las options controlan ordering, frozen, keyword-only y slots.

```python
from dataclasses import dataclass

@dataclass(frozen=True, slots=True)
class User:
    id: int
    name: str
```

Frozen impide assignment normal, pero no deep-freeze de values internos. Usa dataclass para tipos data-oriented y una class normal cuando invariants/behavior dominen. En APIs públicas, elige el recurso que comunique mejor el contrato en vez de depender solo de comodidad sintáctica.
