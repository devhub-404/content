# Imports Absolutos, Relativos y Dinámicos

Los absolute imports nombran modules desde el import path, los relative imports navegan dentro del package actual e `importlib` expone dynamic loading. La resolución depende del package context y `sys.path`.

```python
from app.services import billing
from .models import User

import importlib
plugin = importlib.import_module("plugins.example")
```

Prefiere layouts explícitos y absolute imports en apps grandes. Los dynamic imports sirven para plugins/features opcionales, no para ocultar dependencies normales.
