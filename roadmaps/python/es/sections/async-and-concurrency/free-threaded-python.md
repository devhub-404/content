# Python Free-threaded

Python 3.14 soporta oficialmente un build CPython free-threaded opcional con GIL deshabilitable, permitiendo threads Python en múltiples cores. Es una opción soportada, no el único/default runtime en toda instalación.

```python
import sys

if hasattr(sys, "_is_gil_enabled"):
    print("GIL enabled:", sys._is_gil_enabled())
```

Aun así hay que sincronizar shared mutable state y no depender de efectos históricos del GIL. Extensions incompatibles pueden reactivar el GIL.
