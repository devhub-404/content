# Storage e Web Workers

`localStorage` e `sessionStorage` armazenam dados síncronos string chave/valor. Local storage pode persistir entre sessões conforme política do navegador; session storage também é limitada à sessão da página. São úteis para preferências ou estado modestos, não bancos grandes. Valores estruturados exigem serialização.

```js
localStorage.setItem("theme", "dark");
const theme = localStorage.getItem("theme");

const worker = new Worker("./worker.js", { type: "module" });
worker.postMessage({ values: largeArray });
```

Web Workers executam JavaScript em outro contexto e podem mover computação pesada para fora da main thread da página. Workers não manipulam diretamente o DOM e comunicam-se principalmente por mensagens com structured clone e transferable objects quando suportados. Use quando profiling mostrar computação cara na main thread; messaging e lifecycle também têm custo.
