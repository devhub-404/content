# Cancellation Tokens

`CancellationToken` represents cooperative cancellation. A caller passes a token through operations, and cancellable code observes it directly or forwards it to APIs that support cancellation. Cancellation does not forcibly kill arbitrary code.

```csharp
using var timeout = new CancellationTokenSource(
    TimeSpan.FromSeconds(5));

await service.RunAsync(timeout.Token);
```

Accept a token in long-running or I/O APIs when callers need lifecycle control, propagate it consistently, and distinguish cancellation from unrelated failures. Dispose token sources that own timers or registrations when their lifetime ends.
