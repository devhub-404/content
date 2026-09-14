# `HttpClient` y Requests de Red

`HttpClient` envía requests HTTP async y expone headers, status, content y cancelación. Está diseñado para reutilizarse manteniendo connection pools; crear un client nuevo por request puede perjudicar la red.

```csharp
using var request = new HttpRequestMessage(
    HttpMethod.Get,
    new UriBuilder("https", "example.test", -1, "/api/users").Uri);

using HttpResponseMessage response =
    await client.SendAsync(request, cancellationToken);

response.EnsureSuccessStatusCode();
```

HTTP de producción también necesita timeout, retries seguros, streaming, autenticación y error handling. Un status HTTP no-success es un resultado del protocolo, no lo mismo que una network exception.
