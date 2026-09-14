# Threads, Locks, and Concurrent Collections

When multiple threads access shared mutable state, synchronization is required. `lock` provides mutual exclusion through a monitor, and .NET also offers semaphores, reader/writer locks, interlocked atomics, channels, and concurrent collections for different coordination patterns.

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

Prefer avoiding shared mutable state where practical. Keep lock scopes small, never rely on timing for correctness, and establish a lock order when code may acquire several locks. Async code generally needs async-aware primitives rather than holding a synchronous lock across `await`.
