# Parallel Streams

Parallel streams podem dividir pipelines no common fork/join pool. Podem ajudar trabalho CPU-bound grande, stateless e facilmente splittable, mas possuem overhead e efeitos compartilhados no runtime.

```java
long count = values.parallelStream()
    .filter(this::expensiveCheck)
    .count();
```

Não adicione `parallel()` como botão mágico. Meça workloads, evite I/O bloqueante/shared mutable state e use abstrações dedicadas quando precisa controlar executor/capacity.
