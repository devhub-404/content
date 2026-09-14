# Threads, Locks y Concurrent Collections

Cuando varios threads acceden a estado mutable compartido, hace falta sincronización. `lock` ofrece mutual exclusion, y .NET también ofrece semaphores, reader/writer locks, atomics, channels y concurrent collections.

```csharp
private readonly object _gate = new();
private int _count;

void Increment()
{
    lock (_gate)
    {
        _count++;
    }
}
```

Prefiere evitar shared mutable state. Mantén los lock scopes pequeños, no dependas del timing para la corrección y define un orden al adquirir varios locks. El código async suele necesitar primitives async-aware en vez de mantener un lock síncrono durante `await`.
