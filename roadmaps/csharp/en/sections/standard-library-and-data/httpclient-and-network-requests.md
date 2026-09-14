# `HttpClient` and Network Requests

`HttpClient` sends HTTP requests asynchronously and exposes headers, status, content, and cancellation. It is designed to be reused so connection pools remain effective; creating and disposing a fresh client for every request can harm network behavior.

```csharp
using var request = new HttpRequestMessage(
    HttpMethod.Get,
    new UriBuilder("https", "example.test", -1, "/api/users").Uri);

using HttpResponseMessage response =
    await client.SendAsync(request, cancellationToken);

response.EnsureSuccessStatusCode();
```

Production HTTP also needs timeouts, retries only where safe, streaming for large bodies, authentication, proxy/TLS behavior, and structured error handling. Treat non-success HTTP status as a protocol result, not the same thing as a network exception.
