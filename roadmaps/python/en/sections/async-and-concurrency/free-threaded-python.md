# Free-threaded Python

Python 3.14 officially supports an optional free-threaded CPython build where the GIL can be disabled, allowing Python threads to run bytecode in parallel on multiple cores. It is a supported build option, not the only or default execution model in every installation.

```python
import sys

if hasattr(sys, "_is_gil_enabled"):
    print("GIL enabled:", sys._is_gil_enabled())
```

Code must still synchronize shared mutable state; do not rely on historical GIL side effects for thread safety. Some extension modules can re-enable the GIL if they are not free-threading compatible, so deployment compatibility needs testing.
