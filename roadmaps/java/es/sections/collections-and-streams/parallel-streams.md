# Parallel Streams

Los parallel streams pueden dividir pipelines en el common fork/join pool. Pueden ayudar con trabajo CPU-bound grande, stateless y fácilmente splittable, pero tienen overhead y efectos compartidos en el runtime.

```java
long count = values.parallelStream()
    .filter(this::expensiveCheck)
    .count();
```

No añadas `parallel()` como botón mágico. Mide workloads, evita I/O bloqueante/shared mutable state y usa abstracciones dedicadas cuando necesites controlar executor/capacity.
