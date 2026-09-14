# Transitions and Deferred Values

Solid transitions coordinate lower-priority updates that may trigger async or expensive reactive work, while `createDeferred` creates a value that can lag behind a rapidly changing source. They help preserve responsive interaction while slower UI catches up.

```tsx
const [pending, start] = useTransition();

function selectTab(id) {
  start(() => setTab(id));
}

const deferredQuery = createDeferred(query);
```

These primitives do not make expensive algorithms free. Use them when the product benefits from keeping old content or urgent input responsive, then profile the actual slow computation or request. Loading and stale-state feedback should remain understandable to the user.
