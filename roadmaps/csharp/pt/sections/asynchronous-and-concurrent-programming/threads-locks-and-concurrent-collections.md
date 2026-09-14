# Threads, Locks e Concurrent Collections

Quando múltiplos threads acessam estado mutável compartilhado, sincronização é necessária. `lock` fornece mutual exclusion, e .NET também oferece semaphores, reader/writer locks, atomics, channels e concurrent collections.

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

Prefira evitar shared mutable state. Mantenha lock scopes pequenos, nunca dependa de timing para correção e defina ordem ao adquirir vários locks. Código async normalmente precisa primitives async-aware em vez de segurar lock síncrono através de `await`.
