# Generators and Async Generators

A generator function declared with `function*` can pause at `yield` and resume later. Calling it returns an object that is both iterable and iterator, which makes lazy sequences and explicit state machines concise. `yield*` delegates to another iterable.

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

Async generators combine `async function*`, `await`, and `yield` to produce asynchronous sequences consumed with `for await...of`. They are useful for paginated data, streams, and message sources where each next value may require asynchronous work. When consumers stop early, cleanup behavior still matters for underlying resources.
