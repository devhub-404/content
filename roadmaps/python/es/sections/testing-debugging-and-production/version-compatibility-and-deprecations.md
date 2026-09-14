# Versiones Python, Compatibilidad y Deprecations

Las releases añaden lenguaje, stdlib, optimizations, deprecations y removals. El proyecto debe declarar minimum Python y probar ese floor, no solo el interpreter más nuevo de los developers.

```python
import sys

if sys.version_info < (3, 14):
    raise RuntimeError("Python 3.14+ required")
```

Las libraries suelen soportar varias minors con conditional imports/backports. Las apps pueden avanzar más rápido, pero dependencies/deploy aún necesitan wheels/runtime compatibles.
