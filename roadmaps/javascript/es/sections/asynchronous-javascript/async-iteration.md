# Iteración asíncrona

Async iteration modela secuencias donde obtener el siguiente valor requiere trabajo asíncrono. Un async iterable implementa `[Symbol.asyncIterator]()` y se consume con `for await...of`; los async generators son una forma directa de implementarlo.

```js
async function* pages(loadPage) {
  let page = 1;

  while (true) {
    const result = await loadPage(page++);
    if (result.length === 0) return;
    yield result;
  }
}

for await (const page of pages(loadPage)) {
  console.log(page);
}
```

Es útil para APIs paginadas, streams y mensajes. También expresa backpressure de forma natural porque el consumidor pide y espera cada siguiente valor. Si la iteración termina antes de tiempo, el producer debe limpiar recursos, subscriptions o streams abiertos.
