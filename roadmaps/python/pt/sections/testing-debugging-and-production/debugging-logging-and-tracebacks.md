# Debugging, Logging e Tracebacks

Tracebacks mostram call path/context, `breakpoint()` entra no debugger e `logging` fornece diagnostics por níveis. IDEs e `pdb` permitem stepping/watches.

```python
import logging

logger = logging.getLogger(__name__)

try:
    process()
except Exception:
    logger.exception("processing failed")
    raise
```

Logue na layer que possui contexto operacional em vez de repetir o mesmo erro. Preserve traceback ao re-raise e não exponha secrets em logs.
