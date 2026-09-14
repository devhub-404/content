# DevTools and Reactive Debugging

Solid DevTools and focused logging can reveal component ownership, signals, computations, and updates. Because a component does not rerender in the React sense, debugging should follow the reactive graph: which source changed, which computation subscribed, and which DOM expression updated.

```tsx
createEffect(() => {
  console.debug({
    query: query(),
    resultCount: filtered().length
  });
});
```

Do not add permanent effects merely to inspect state; remove temporary diagnostics after the problem is understood. When performance matters, inspect expensive computations, large list reconciliation, async waterfalls, and unnecessary external work rather than counting component function calls as a proxy for cost.
