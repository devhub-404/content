# Parallel Streams

Parallel streams can divide compatible pipelines across the common fork/join pool. They may help CPU-bound, sufficiently large, stateless operations with splittable sources, but parallelism has overhead and shared runtime consequences.

```java
long count = values.parallelStream()
    .filter(this::expensiveCheck)
    .count();
```

Do not add `parallel()` as a generic performance switch. Measure realistic workloads, avoid blocking I/O and shared mutable state inside the pipeline, and consider dedicated concurrency abstractions when you need explicit executor or capacity control.
