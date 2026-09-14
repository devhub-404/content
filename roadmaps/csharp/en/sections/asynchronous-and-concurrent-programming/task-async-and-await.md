# `Task`, `async`, and `await`

An `async` method usually returns `Task`, `Task<T>`, or another awaitable type. `await` asynchronously waits for completion and lets the method resume later without blocking the current thread for I/O-bound work. The compiler transforms the method into a state machine.

```csharp
static async Task<string> LoadAsync(
    HttpClient client,
    string url,
    CancellationToken token)
{
    return await client.GetStringAsync(url, token);
}
```

Async does not automatically create a new thread and does not make CPU-heavy work cheaper. Keep async all the way through I/O call chains and avoid `.Result` or `.Wait()` in code that can instead await the operation.
