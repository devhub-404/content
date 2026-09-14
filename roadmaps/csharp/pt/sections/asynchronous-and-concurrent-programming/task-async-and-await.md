# `Task`, `async` e `await`

Método `async` normalmente retorna `Task`, `Task<T>` ou outro awaitable. `await` espera sem bloquear o thread durante I/O e o compilador transforma o método em state machine.

```csharp
static async Task<string> LoadAsync(
    HttpClient client,
    string url,
    CancellationToken token)
{
    return await client.GetStringAsync(url, token);
}
```

Async não cria thread automaticamente e não torna CPU-heavy work barato. Mantenha async por toda cadeia de I/O e evite `.Result`/`.Wait()` quando a operação pode ser aguardada com `await`.
