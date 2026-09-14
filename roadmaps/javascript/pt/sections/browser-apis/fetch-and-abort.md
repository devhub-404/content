# Fetch e Cancelamento

Fetch retorna Promise para uma `Response` HTTP. Essa promise normalmente rejeita por falha de rede ou cancelamento, não apenas porque o servidor respondeu 404 ou 500, então a aplicação deve inspecionar `response.ok` ou `status`. Bodies podem ser consumidos como JSON, texto, Blob, ArrayBuffer ou streams de baixo nível.

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

`AbortController` fornece cancelamento por `AbortSignal` e funciona com várias outras APIs do navegador. Cancelamento importa quando requests deixam de ser relevantes por navegação, novo input ou teardown. CORS, credentials, cache, redirects e semântica HTTP são preocupações distintas; configure deliberadamente em vez de tratar Fetch apenas como “AJAX com promises”.
