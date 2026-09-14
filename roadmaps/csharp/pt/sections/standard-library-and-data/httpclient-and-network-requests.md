# `HttpClient` e Requests de Rede

`HttpClient` envia requests HTTP async e expõe headers, status, content e cancellation. Ele foi feito para reuse, mantendo connection pools; criar um client novo por request pode prejudicar comportamento de rede.

```csharp
using var request = new HttpRequestMessage(
    HttpMethod.Get,
    new UriBuilder("https", "example.test", -1, "/api/users").Uri);

using HttpResponseMessage response =
    await client.SendAsync(request, cancellationToken);

response.EnsureSuccessStatusCode();
```

HTTP de produção também precisa timeout, retries seguros, streaming, autenticação e error handling. Status HTTP não-success é resultado de protocolo, não a mesma coisa que network exception.
