# Garbage Collection y Reachability

La JVM libera heap objects unreachable automáticamente y ofrece collectors con distintos objetivos de latency/throughput. El lifetime depende de reachability, no solo del scope léxico.

```java
List<byte[]> cache = new ArrayList<>();
cache.add(new byte[1024]);

// Objects are collectible once no live roots reach them.
```

La managed memory puede filtrar cuando caches, statics, listeners, threads o collections retienen objetos. Usa heap dumps/profilers para encontrar retention paths en vez de `System.gc()`.
