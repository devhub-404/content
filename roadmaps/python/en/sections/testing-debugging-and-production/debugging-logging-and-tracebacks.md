# Debugging, Logging, and Tracebacks

Tracebacks show the call path and exception context, `breakpoint()` enters the configured debugger, and the `logging` module provides leveled structured application diagnostics. IDEs and `pdb` add stepping, watches, and frame inspection.

```python
import logging

logger = logging.getLogger(__name__)

try:
    process()
except Exception:
    logger.exception("processing failed")
    raise
```

Log at the layer that owns operational context instead of logging the same exception at every level. Preserve tracebacks when re-raising, and never put secrets or full sensitive payloads into routine logs.
