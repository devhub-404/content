# Threads and Executors

Raw `Thread` objects represent platform-managed threads, while executor services separate task submission from scheduling and worker management. Thread pools are useful when concurrency must be bounded or shared among many tasks.

```java
try (var executor = Executors.newFixedThreadPool(4)) {
    for (Runnable task : tasks) {
        executor.submit(task);
    }
}
```

Prefer executors and higher-level coordination over manually creating and tracking many threads. Define shutdown behavior explicitly so applications do not leak workers or abandon important tasks during process termination.
