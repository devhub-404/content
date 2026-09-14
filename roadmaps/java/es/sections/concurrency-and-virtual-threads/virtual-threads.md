# Virtual Threads

Los virtual threads son threads Java ligeros para escalar el estilo thread-per-task en workloads que pasan mucho tiempo esperando I/O bloqueante. Usan el modelo familiar de `Thread`, executor y synchronization.

```java
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    Future<String> result = executor.submit(() -> loadData());
    System.out.println(result.get());
}
```

No vuelven paralelo el trabajo CPU sin límites y no necesitan pool solo para reducir su cantidad. Sigue limitando recursos escasos como conexiones, cuotas y memoria mediante controles de capacidad.
