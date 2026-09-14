# `Any`, Casts, and Runtime Validation

`Any` disables most static checking for operations involving that value, and `typing.cast` tells a checker to trust a type without performing a runtime conversion or validation. These are escape hatches, not proof that data has the claimed shape.

```python
from typing import Any, cast

raw: Any = load_external()
name = cast(str, raw)  # static assertion only

if not isinstance(raw, str):
    raise TypeError("expected string")
```

At JSON, database, environment, plugin, and other trust boundaries, validate runtime data with explicit checks or a schema library. Keep `Any` near the boundary so uncertainty does not spread through the entire program.
