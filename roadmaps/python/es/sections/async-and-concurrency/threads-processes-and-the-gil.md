# Threads, Processes y GIL

En CPython estándar, el GIL limita la ejecución simultánea de bytecode, pero los threads son útiles para blocking I/O y extensions que liberan el GIL. Los procesos usan interpreters separados y paralelismo real.

```python
from concurrent.futures import ThreadPoolExecutor

with ThreadPoolExecutor() as pool:
    results = list(pool.map(fetch, urls))
```

Elige según workload: asyncio para async I/O, threads para blocking I/O compatible y processes para CPU isolation/parallelism. Mide overhead.
