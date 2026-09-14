# Server Rendering com Streaming

APIs de server do React podem streamar HTML em vez de esperar tree inteira. Suspense boundaries permitem enviar partes prontas enquanto regiões lentas continuam renderizando, melhorando first content e progressive reveal.

```jsx
const stream = await renderToReadableStream(
  <App />,
  { onError(error) { console.error(error); } }
);

return new Response(stream, {
  headers: { 'Content-Type': 'text/html' }
});
```

Streaming muda error handling e timing da response: headers podem estar committed antes de falha posterior, e crawlers/static generation podem preferir esperar mais conteúdo. Frameworks normalmente encapsulam isso com routing, data, cache e deployment.
