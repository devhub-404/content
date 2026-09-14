# Dataclasses

`dataclass` gera `__init__`, `__repr__`, equality e outros a partir de fields anotados. Options controlam ordering, frozen, keyword-only e slots.

```python
from dataclasses import dataclass

@dataclass(frozen=True, slots=True)
class User:
    id: int
    name: str
```

Frozen impede assignment normal, mas não deep-freeze de values internos. Use dataclass para tipos data-oriented e class comum quando invariants/behavior dominam. Em APIs públicas, escolha o recurso que comunica melhor o contrato em vez de depender apenas de conveniência sintática.
