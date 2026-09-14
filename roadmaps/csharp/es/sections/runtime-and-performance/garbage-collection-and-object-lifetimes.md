# Garbage Collection y Lifetimes de Objetos

.NET usa un garbage collector generacional para managed memory. Los objetos siguen vivos mientras sean reachable desde GC roots y el momento de la colección es no determinista. El cleanup de memoria es distinto del disposal determinista de recursos.

```csharp
byte[] buffer = new byte[4096];

// The GC reclaims managed memory once it is unreachable.
UseBuffer(buffer);
```

Los leaks en código gestionado suelen ser reachability accidental: caches, static events, colecciones long-lived, closures o background work. Diagnostica retención con profiler en vez de forzar GC manualmente.
