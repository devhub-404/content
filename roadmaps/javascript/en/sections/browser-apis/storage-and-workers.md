# Storage and Web Workers

`localStorage` and `sessionStorage` store synchronous string key/value data. Local storage can persist across sessions according to browser policy; session storage is additionally scoped to a page session. They are useful for modest preferences or state, not large databases. Structured values require serialization.

```js
localStorage.setItem("theme", "dark");
const theme = localStorage.getItem("theme");

const worker = new Worker("./worker.js", { type: "module" });
worker.postMessage({ values: largeArray });
```

Web Workers run JavaScript in another worker context and can move CPU-heavy computation off the page's main thread. Workers cannot directly manipulate the page DOM and communicate primarily through messages using structured cloning and transferable objects where supported. Use them when profiling shows expensive main-thread computation; messaging and lifecycle have their own cost.
