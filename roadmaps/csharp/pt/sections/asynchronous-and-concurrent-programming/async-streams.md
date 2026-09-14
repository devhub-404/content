# Async Streams com `IAsyncEnumerable<T>`

`IAsyncEnumerable<T>` modela sequência cujo próximo elemento pode exigir trabalho assíncrono. Async iterators combinam `async` e `yield return`, e consumers usam `await foreach`.

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

Async streams servem a APIs paginadas, feeds, database streaming e pipelines onde bufferizar tudo é desperdício. Projete cancellation/disposal para que saída antecipada libere o recurso subjacente.
