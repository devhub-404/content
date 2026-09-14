# Texto, Libraries JSON e HTTP

A standard library inclui HTTP client, charsets, URI/URL e I/O amplo, enquanto object mapping JSON normalmente vem de libraries do ecossistema.

```java
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder(uri).GET().build();
HttpResponse<String> response = client.send(
    request,
    HttpResponse.BodyHandlers.ofString());
```

Separe status HTTP, falha de transporte, decoding e validação de domínio. Reuse `HttpClient`, configure timeouts e mantenha DTO contracts separados das invariantes do domínio quando formatos podem evoluir.
