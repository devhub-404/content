# `Any`, Casts e Validação Runtime

`Any` desliga grande parte do static checking e `typing.cast` apenas convence o checker; não converte nem valida runtime.

```python
from typing import Any, cast

raw: Any = load_external()
name = cast(str, raw)  # static assertion only

if not isinstance(raw, str):
    raise TypeError("expected string")
```

Em JSON, database, env e plugin boundaries, valide dados explicitamente ou com schema library. Mantenha `Any` perto da boundary para não espalhar incerteza.
