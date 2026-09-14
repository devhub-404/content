# Debugging, Logging y Tracebacks

Los tracebacks muestran call path/context, `breakpoint()` entra al debugger y `logging` ofrece diagnostics por niveles. IDEs y `pdb` permiten stepping/watches.

```python
import logging

logger = logging.getLogger(__name__)

try:
    process()
except Exception:
    logger.exception("processing failed")
    raise
```

Haz log en la capa que posee contexto operacional en vez de repetir el mismo error. Conserva traceback al re-raise y no expongas secrets en logs.
