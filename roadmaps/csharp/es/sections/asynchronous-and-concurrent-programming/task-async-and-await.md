# `Task`, `async` y `await`

Un método `async` suele retornar `Task`, `Task<T>` u otro awaitable. `await` espera sin bloquear el thread durante I/O y el compilador transforma el método en una state machine.

```csharp
static async Task<string> LoadAsync(
    HttpClient client,
    string url,
    CancellationToken token)
{
    return await client.GetStringAsync(url, token);
}
```

Async no crea un thread automáticamente ni vuelve barato el trabajo CPU-heavy. Mantén async en toda la cadena de I/O y evita `.Result`/`.Wait()` cuando la operación pueda esperarse con `await`.
