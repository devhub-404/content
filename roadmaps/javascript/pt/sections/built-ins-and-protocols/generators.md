# Generators e Async Generators

Uma generator function declarada com `function*` pode pausar em `yield` e continuar depois. Chamá-la retorna objeto que é iterable e iterator, tornando sequências lazy e máquinas de estado explícitas mais concisas. `yield*` delega para outro iterable.

```js
function* ids() {
  let id = 1;
  while (true) {
    yield id++;
  }
}

async function* pages(loadPage) {
  for (let page = 1; ; page++) {
    const items = await loadPage(page);
    if (items.length === 0) return;
    yield items;
  }
}
```

Async generators combinam `async function*`, `await` e `yield` para produzir sequências assíncronas consumidas com `for await...of`. São úteis para dados paginados, streams e fontes de mensagens onde cada próximo valor pode exigir trabalho assíncrono. Quando consumidores param cedo, o comportamento de cleanup ainda importa para recursos subjacentes.
