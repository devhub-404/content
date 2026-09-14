# Promise Composition

Promise combinators encode concurrency policies. `Promise.all()` requires every input and rejects on the first rejection. `allSettled()` waits for every outcome. `race()` settles with the first settled input, while `any()` fulfills with the first fulfillment and rejects only if all inputs reject.

```js
const [user, settings] = await Promise.all([
  loadUser(),
  loadSettings(),
]);

const first = await Promise.any([
  fetchFromPrimary(),
  fetchFromReplica(),
]);
```

Starting independent operations before awaiting them allows concurrency; consecutive awaits can accidentally serialize work. Composition does not automatically cancel losing or failed operations. Cancellation normally comes from the host API—such as `AbortController` for Fetch—and must be wired separately when abandoned work is expensive or causes side effects.
