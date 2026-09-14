# Imports Absolutos, Relativos e Dinâmicos

Absolute imports nomeiam modules pelo import path, relative imports navegam no package atual e `importlib` expõe dynamic loading. Resolução depende do package context e `sys.path`.

```python
from app.services import billing
from .models import User

import importlib
plugin = importlib.import_module("plugins.example")
```

Prefira layouts explícitos e absolute imports em apps grandes. Dynamic imports servem a plugins/features opcionais, não para esconder dependency comum.
