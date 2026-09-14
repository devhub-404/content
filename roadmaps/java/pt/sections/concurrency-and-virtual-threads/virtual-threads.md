# Virtual Threads

Virtual threads são threads Java leves para escalar estilo thread-per-task em workloads que passam muito tempo esperando I/O bloqueante. Usam o modelo familiar de `Thread`, executor e synchronization.

```java
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    Future<String> result = executor.submit(() -> loadData());
    System.out.println(result.get());
}
```

Não tornam CPU work paralelo sem limite e não precisam de pool só para reduzir quantidade. Ainda limite recursos escassos como conexões, quotas e memória com controles de capacidade.
