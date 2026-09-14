# Garbage Collection and Object Lifetimes

.NET uses a generational garbage collector for managed memory. Objects remain alive while reachable from GC roots, and collection timing is intentionally nondeterministic. Managed memory cleanup is therefore different from deterministic resource disposal.

```csharp
byte[] buffer = new byte[4096];

// The GC reclaims managed memory once it is unreachable.
UseBuffer(buffer);
```

Memory leaks in managed programs are usually accidental reachability: caches, static events, long-lived collections, closures, or background work keep objects alive. Diagnose retention with profilers rather than manually forcing garbage collections.
