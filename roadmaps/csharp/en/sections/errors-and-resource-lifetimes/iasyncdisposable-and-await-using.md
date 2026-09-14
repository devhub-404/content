# `IAsyncDisposable` and `await using`

Some resources need asynchronous cleanup because releasing them may flush network data, complete protocol shutdown, or perform other asynchronous work. `IAsyncDisposable.DisposeAsync` and `await using` integrate that lifetime with async methods.

```csharp
await using var connection =
    await OpenConnectionAsync(cancellationToken);

await connection.SendAsync(data, cancellationToken);
```

Choose synchronous or asynchronous disposal according to the resource contract rather than using async cleanup everywhere. If a type implements both forms, document which one callers should prefer and whether either can block.
