# Streaming Server Rendering

React server APIs can stream HTML instead of waiting for the entire tree to finish. Suspense boundaries let ready portions of the page reach the client while slower regions continue rendering, improving time-to-first-content and allowing progressive reveal.

```jsx
const stream = await renderToReadableStream(
  <App />,
  { onError(error) { console.error(error); } }
);

return new Response(stream, {
  headers: { 'Content-Type': 'text/html' }
});
```

Streaming changes error handling and response timing: headers may be committed before later work fails, and crawlers or static generation may prefer to wait for more content. Application frameworks normally wrap these details with routing, data loading, caching, and deployment-specific behavior.
