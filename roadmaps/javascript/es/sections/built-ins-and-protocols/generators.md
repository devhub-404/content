# Generators y async generators

Una generator function declarada con `function*` puede pausar en `yield` y continuar después. Su llamada devuelve un objeto iterable e iterator, lo que simplifica secuencias lazy y máquinas de estado. `yield*` delega en otro iterable.

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

Los async generators combinan `async function*`, `await` y `yield` y se consumen con `for await...of`. Encajan bien en paginación, streams y fuentes de mensajes. Si el consumidor abandona pronto la iteración, el productor todavía debe liberar correctamente recursos subyacentes.
