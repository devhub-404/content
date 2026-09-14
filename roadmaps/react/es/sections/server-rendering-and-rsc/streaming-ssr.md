# Server Rendering con Streaming

Las APIs de server de React pueden streamear HTML en vez de esperar todo el tree. Suspense boundaries permiten enviar partes listas mientras regiones lentas siguen renderizando, mejorando first content y progressive reveal.

```jsx
const stream = await renderToReadableStream(
  <App />,
  { onError(error) { console.error(error); } }
);

return new Response(stream, {
  headers: { 'Content-Type': 'text/html' }
});
```

Streaming cambia error handling y timing de la response: headers pueden estar committed antes de un fallo posterior y crawlers/static generation pueden preferir esperar más contenido. Los frameworks normalmente encapsulan esto con routing, data, cache y deployment.
