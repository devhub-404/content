# Threads, Processes, and the GIL

In standard CPython builds, the Global Interpreter Lock limits simultaneous execution of Python bytecode in one process, but threads remain useful for blocking I/O and C extensions that release the GIL. Multiple processes provide separate interpreters and true process-level parallelism.

```python
from concurrent.futures import ThreadPoolExecutor

with ThreadPoolExecutor() as pool:
    results = list(pool.map(fetch, urls))
```

Choose concurrency from the workload: asyncio for async I/O, threads for compatible blocking I/O and shared-memory coordination, processes for CPU isolation/parallelism. Measure serialization and process-start overhead before assuming more workers are faster.
