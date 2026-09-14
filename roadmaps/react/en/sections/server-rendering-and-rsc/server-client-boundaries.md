# Server and Client Component Boundaries

The `'use client'` directive marks a module whose exported components participate in the client bundle. Server-rendered parents can pass serializable data and rendered children across that boundary, letting most of a page stay on the server while small interactive islands run in the browser.

```jsx
// Counter.jsx
'use client';

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

Treat the boundary as a bundle and serialization decision, not merely a syntax requirement. Keep client modules narrow when server rendering can do the rest. Values crossing from server to client must follow the supported serialization model, and server-only secrets must never be included in client props.
