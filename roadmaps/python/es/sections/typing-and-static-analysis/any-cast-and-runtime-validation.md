# `Any`, Casts y Validación Runtime

`Any` desactiva gran parte del static checking y `typing.cast` solo convence al checker; no convierte ni valida en runtime.

```python
from typing import Any, cast

raw: Any = load_external()
name = cast(str, raw)  # static assertion only

if not isinstance(raw, str):
    raise TypeError("expected string")
```

En boundaries de JSON, database, env y plugins, valida los datos explícitamente o con una schema library. Mantén `Any` cerca del boundary para no propagar incertidumbre.
