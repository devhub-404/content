# Text, JSON Libraries, and HTTP

The standard library includes HTTP client APIs, charset handling, URI/URL types, and broad I/O support, while JSON serialization is commonly supplied by ecosystem libraries rather than one universal built-in object mapper.

```java
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder(uri).GET().build();
HttpResponse<String> response = client.send(
    request,
    HttpResponse.BodyHandlers.ofString());
```

Treat network status codes, transport failures, decoding failures, and domain validation as separate layers. Reuse `HttpClient`, set timeouts where appropriate, and keep DTO serialization contracts independent from core domain invariants when formats may evolve.
