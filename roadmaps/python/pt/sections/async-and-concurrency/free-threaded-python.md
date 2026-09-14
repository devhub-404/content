# Python Free-threaded

Python 3.14 suporta oficialmente build CPython free-threaded opcional com GIL desabilitável, permitindo threads Python em múltiplos cores. É opção suportada, não único/default runtime em toda instalação.

```python
import sys

if hasattr(sys, "_is_gil_enabled"):
    print("GIL enabled:", sys._is_gil_enabled())
```

Ainda é preciso sincronizar shared mutable state e não depender de efeitos históricos do GIL. Extensions incompatíveis podem reativar GIL.
