# `IAsyncDisposable` y `await using`

Algunos recursos necesitan cleanup asíncrono porque liberar puede hacer flush de red o cerrar protocolos. `IAsyncDisposable.DisposeAsync` y `await using` integran ese lifetime con métodos async.

```csharp
await using var connection =
    await OpenConnectionAsync(cancellationToken);

await connection.SendAsync(data, cancellationToken);
```

Elige disposal síncrono o asíncrono según el contrato, no uses async por defecto. Si un tipo implementa ambos, documenta cuál deberían preferir los callers y si alguno puede bloquear.
