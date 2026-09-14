# Fetch y cancelación

Fetch devuelve una Promise con una `Response`. Esa promise rechaza normalmente por fallo de red o cancelación, no solo porque el servidor responda 404 o 500, por lo que el código debe comprobar `response.ok` o `status`. El body puede consumirse como JSON, texto, Blob, ArrayBuffer o stream.

```js
const controller = new AbortController();

const response = await fetch("/api/users", {
  signal: controller.signal,
});

if (!response.ok) {
  throw new Error(`HTTP ${response.status}`);
}

const users = await response.json();
```

`AbortController` proporciona cancelación mediante `AbortSignal` y funciona con varias APIs del navegador. Cancela trabajo que dejó de ser relevante por navegación, nuevo input o teardown. CORS, credentials, caché y redirects son problemas HTTP/plataforma separados y deben configurarse deliberadamente.
