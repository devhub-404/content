# Versões Python, Compatibilidade e Deprecations

Releases adicionam linguagem, stdlib, optimizations, deprecations e removals. O projeto deve declarar minimum Python e testar esse floor, não só o interpreter mais novo dos developers.

```python
import sys

if sys.version_info < (3, 14):
    raise RuntimeError("Python 3.14+ required")
```

Libraries normalmente suportam várias minors com conditional imports/backports. Apps podem mover mais rápido, mas dependencies/deploy ainda precisam wheels/runtime compatíveis.
