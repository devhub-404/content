# Virtual Threads

Virtual threads are lightweight Java threads designed to make thread-per-task style scalable for workloads that spend much of their time waiting on blocking I/O. They use the familiar `Thread`, executor, synchronization, and stack-trace programming model.

```java
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    Future<String> result = executor.submit(() -> loadData());
    System.out.println(result.get());
}
```

Virtual threads do not make CPU work parallel without limits and should not be pooled merely to reduce their count. Still limit scarce external resources such as database connections, API quotas, and memory through semaphores or other capacity controls.
