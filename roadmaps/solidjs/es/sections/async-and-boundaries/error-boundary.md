# Error Boundaries

`ErrorBoundary` captura errors lanzados al crear/actualizar el reactive subtree debajo y renderiza fallback. El fallback puede recibir reset para intentar de nuevo después de que cambie la condición subyacente.

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

Usa boundaries en regiones significativas y reporta errors a monitoring en vez de solo ocultarlos. No sustituyen expected-error states normales de data APIs; validation failures y not-found suelen ser domain values, no exceptions para derribar un subtree.
