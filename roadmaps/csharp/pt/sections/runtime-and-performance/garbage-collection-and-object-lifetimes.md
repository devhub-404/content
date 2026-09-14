# Garbage Collection e Lifetimes de Objetos

.NET usa garbage collector geracional para managed memory. Objetos permanecem vivos enquanto reachable por GC roots e o momento da coleta é não determinístico. Cleanup de memória é diferente de disposal determinístico de recursos.

```csharp
byte[] buffer = new byte[4096];

// The GC reclaims managed memory once it is unreachable.
UseBuffer(buffer);
```

Leaks em código gerenciado normalmente são reachability acidental: caches, static events, collections long-lived, closures ou background work. Diagnostique retenção com profiler em vez de forçar GC manualmente.
