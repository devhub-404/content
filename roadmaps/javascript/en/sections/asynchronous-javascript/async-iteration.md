# Async Iteration

Async iteration represents a sequence whose next value can require asynchronous work. An async iterable provides `[Symbol.asyncIterator]()` and is consumed with `for await...of`. Async generators implement the protocol with ordinary-looking control flow.

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

This model fits paginated APIs, streams, and message sources. It also expresses backpressure naturally because the consumer asks for and awaits each next value. When an iteration stops early, iterator cleanup and any underlying resource lifecycle still matter; production code should not leave streams, subscriptions, or handles open.
