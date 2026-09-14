# Reactive Owners and `createRoot`

Reactive computations belong to owners that control cleanup and lifetime. Components create ownership scopes automatically, while `createRoot` creates one manually for reactive systems that live outside component rendering. Disposing a root cleans up the computations and registered resources beneath it.

```tsx
const dispose = createRoot(dispose => {
  const [count, setCount] = createSignal(0);
  createEffect(() => console.log(count()));
  setCount(1);
  return dispose;
});

dispose();
```

Understanding ownership prevents leaked effects and resources. If you create reactive work in callbacks or library code outside an owner, decide who will dispose it. Advanced helpers such as `getOwner` and `runWithOwner` can preserve context, but ordinary component ownership is simpler when available.
