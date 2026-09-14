# Garbage Collection and Reachability

The JVM automatically reclaims unreachable heap objects, with several garbage-collector implementations optimized for different latency and throughput goals. Object lifetime is based on reachability, not lexical scope alone.

```java
List<byte[]> cache = new ArrayList<>();
cache.add(new byte[1024]);

// Objects are collectible once no live roots reach them.
```

Managed memory can still leak when caches, static fields, listeners, threads, or collections retain objects longer than intended. Use heap dumps and profilers to find retention paths instead of calling `System.gc()` as a fix.
