# Error Boundaries

`ErrorBoundary` catches errors thrown while creating or updating the reactive subtree below it and renders fallback UI. The fallback can receive a reset function so the failed subtree can be attempted again after the underlying condition changes.

```tsx
<ErrorBoundary fallback={(error, reset) => (
  <div>
    <p>{error.message}</p>
    <button onClick={reset}>Try again</button>
  </div>
)}>
  <Dashboard />
</ErrorBoundary>
```

Use boundaries around meaningful failure regions and report errors to monitoring rather than merely hiding them. Error boundaries do not replace ordinary expected-error states from data APIs. Validation failures and “not found” results are usually domain values, not exceptions that should crash a subtree.
