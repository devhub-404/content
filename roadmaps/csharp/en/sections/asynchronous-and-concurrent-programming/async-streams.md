# Async Streams with `IAsyncEnumerable<T>`

`IAsyncEnumerable<T>` models a sequence whose next element may require asynchronous work. Async iterator methods combine `async` and `yield return`, while consumers use `await foreach` to request values over time.

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

Async streams fit paginated APIs, event feeds, database streaming, and pipelines where buffering every result first would be wasteful. Design cancellation and disposal carefully so an early consumer exit releases the underlying resource.
