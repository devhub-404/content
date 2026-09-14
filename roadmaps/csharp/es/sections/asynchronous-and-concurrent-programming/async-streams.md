# Async Streams con `IAsyncEnumerable<T>`

`IAsyncEnumerable<T>` modela una secuencia cuyo siguiente elemento puede requerir trabajo asíncrono. Los async iterators combinan `async` y `yield return`, y los consumers usan `await foreach`.

```csharp
static async IAsyncEnumerable<int> CountAsync()
{
    for (int i = 0; i < 3; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}

await foreach (int value in CountAsync())
    Console.WriteLine(value);
```

Los async streams sirven para APIs paginadas, feeds, database streaming y pipelines donde bufferizar todo sería costoso. Diseña cancelación/disposal para que una salida temprana libere el recurso subyacente.
