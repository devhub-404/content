# Threads, Processes e GIL

Em CPython padrão, GIL limita execução simultânea de bytecode, mas threads são úteis para blocking I/O e extensions que liberam GIL. Processos usam interpreters separados e paralelismo real.

```python
from concurrent.futures import ThreadPoolExecutor

with ThreadPoolExecutor() as pool:
    results = list(pool.map(fetch, urls))
```

Escolha pelo workload: asyncio para async I/O, threads para blocking I/O compatível e processes para CPU isolation/parallelism. Meça overhead.
