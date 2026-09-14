# `IAsyncDisposable` e `await using`

Alguns recursos precisam cleanup assíncrono porque release pode flush network data ou encerrar protocolos. `IAsyncDisposable.DisposeAsync` e `await using` integram esse lifetime a métodos async.

```csharp
await using var connection =
    await OpenConnectionAsync(cancellationToken);

await connection.SendAsync(data, cancellationToken);
```

Escolha disposal síncrono ou assíncrono conforme o contrato, não use async por padrão. Se um tipo implementa ambos, documente qual callers devem preferir e se algum pode bloquear.
