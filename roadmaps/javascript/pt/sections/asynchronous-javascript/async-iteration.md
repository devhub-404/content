# Iteração Assíncrona

Async iteration representa sequência cujo próximo valor pode exigir trabalho assíncrono. Um async iterable fornece `[Symbol.asyncIterator]()` e é consumido com `for await...of`. Async generators implementam o protocolo com fluxo parecido com código comum.

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

Esse modelo serve para APIs paginadas, streams e fontes de mensagens. Também expressa backpressure naturalmente porque o consumidor solicita e aguarda cada próximo valor. Quando a iteração termina cedo, cleanup do iterator e lifecycle de recursos subjacentes ainda importam; código de produção não deve deixar streams, subscriptions ou handles abertos.
