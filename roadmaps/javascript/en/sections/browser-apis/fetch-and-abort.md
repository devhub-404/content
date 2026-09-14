# Fetch and Cancellation

Fetch returns a Promise for an HTTP `Response`. That promise normally rejects for network-level failure or cancellation, not merely because the server returned 404 or 500, so application code should inspect `response.ok` or `status`. Response bodies can be consumed as JSON, text, Blob, ArrayBuffer, or lower-level streams.

```js
const controller = new AbortController();

const response = await fetch("/api/users", {
  signal: controller.signal,
});

if (!response.ok) {
  throw new Error(`HTTP ${response.status}`);
}

const users = await response.json();
```

`AbortController` provides cancellation through an `AbortSignal` and also works with several other browser APIs. Cancellation is important when requests become irrelevant because of navigation, new input, or component teardown. CORS, credentials, caching, redirects, and HTTP semantics are distinct platform concerns; configure them deliberately rather than treating Fetch as just “AJAX with promises.”
