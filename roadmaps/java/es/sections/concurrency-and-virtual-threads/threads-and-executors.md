# Threads y Executors

`Thread` representa threads gestionados por la plataforma y los executors separan task submission de scheduling/worker management. Los pools ayudan cuando la concurrencia debe limitarse.

```java
try (var executor = Executors.newFixedThreadPool(4)) {
    for (Runnable task : tasks) {
        executor.submit(task);
    }
}
```

Prefiere executors y abstracciones superiores frente a crear/rastrear muchos threads manualmente. Define shutdown explícitamente para no filtrar workers ni abandonar tasks importantes.
