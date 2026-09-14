# `async` and `await`

An `async` function always returns a Promise. `await` pauses that async execution until a promise-like value settles, then produces the fulfillment value or throws the rejection reason. It does not block the entire runtime; other scheduled work can continue while the operation is pending.

```js
async function loadDashboard() {
  const response = await fetch("/api/dashboard");

  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }

  return response.json();
}
```

`try`/`catch` works naturally around awaits. Avoid sequential awaits when work is independent—start the operations together and compose them. Top-level `await` is available in modules, but a module that waits at evaluation time can delay dependent modules. Async/await is structured syntax over Promise semantics, not a different concurrency system.
