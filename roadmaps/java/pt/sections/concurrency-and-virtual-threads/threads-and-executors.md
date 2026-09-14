# Threads e Executors

`Thread` representa threads gerenciados pela plataforma e executors separam task submission de scheduling/worker management. Pools ajudam quando concorrência precisa ser limitada.

```java
try (var executor = Executors.newFixedThreadPool(4)) {
    for (Runnable task : tasks) {
        executor.submit(task);
    }
}
```

Prefira executors e abstrações mais altas a criar/rastrear muitos threads manualmente. Defina shutdown explicitamente para não vazar workers nem abandonar tasks importantes.
