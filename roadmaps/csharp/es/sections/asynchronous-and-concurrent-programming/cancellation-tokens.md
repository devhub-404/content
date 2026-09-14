# Cancellation Tokens

`CancellationToken` representa cancelación cooperativa. El caller pasa el token y el código lo observa o lo reenvía a APIs cancelables. La cancelación no mata código arbitrariamente por la fuerza.

```csharp
using var timeout = new CancellationTokenSource(
    TimeSpan.FromSeconds(5));

await service.RunAsync(timeout.Token);
```

Acepta token en APIs long-running/I/O cuando los callers necesiten control de lifecycle, propágalo consistentemente y distingue cancelación de otros fallos. Dispose los token sources que posean timers/registrations.
