# Absolute, Relative, and Dynamic Imports

Absolute imports name modules from the import path, relative imports navigate within the current package, and `importlib` exposes the import system for dynamic loading. Import resolution depends on package execution context and `sys.path`.

```python
from app.services import billing
from .models import User

import importlib
plugin = importlib.import_module("plugins.example")
```

Prefer explicit package layouts and absolute imports for clarity across large applications. Dynamic imports belong in plugin or optional-feature systems where runtime discovery is deliberate; do not use them to hide ordinary dependencies.
