# Cancellation Tokens

`CancellationToken` representa cancelamento cooperativo. O caller passa o token, e o código o observa ou repassa a APIs cancellable. Cancellation não mata código arbitrariamente à força.

```csharp
using var timeout = new CancellationTokenSource(
    TimeSpan.FromSeconds(5));

await service.RunAsync(timeout.Token);
```

Aceite token em APIs long-running/I/O quando callers precisam lifecycle control, propague de forma consistente e diferencie cancellation de falhas comuns. Dispose token sources que possuem timers/registrations.
