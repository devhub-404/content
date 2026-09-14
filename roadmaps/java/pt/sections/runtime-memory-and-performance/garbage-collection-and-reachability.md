# Garbage Collection e Reachability

JVM libera heap objects unreachable automaticamente e oferece collectors com diferentes metas de latency/throughput. Lifetime depende de reachability, não apenas scope lexical.

```java
List<byte[]> cache = new ArrayList<>();
cache.add(new byte[1024]);

// Objects are collectible once no live roots reach them.
```

Managed memory ainda pode vazar quando caches, statics, listeners, threads ou collections retêm objetos. Use heap dumps/profilers para encontrar retention paths em vez de `System.gc()`.
