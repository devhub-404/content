# Texto, Libraries JSON y HTTP

La standard library incluye HTTP client, charsets, URI/URL e I/O amplio, mientras el object mapping JSON suele venir de libraries del ecosistema.

```java
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder(uri).GET().build();
HttpResponse<String> response = client.send(
    request,
    HttpResponse.BodyHandlers.ofString());
```

Separa status HTTP, fallo de transporte, decoding y validación de dominio. Reutiliza `HttpClient`, configura timeouts y mantén DTO contracts separados de invariantes del dominio cuando los formatos puedan evolucionar.
