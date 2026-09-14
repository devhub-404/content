# Error e Not-found Boundaries

Conventions `error`, `not-found` e `global-error` fornecem fallback por scopes. `notFound()` expressa resource ausente esperado, enquanto Error Boundaries capturam failures inesperadas de rendering.

```tsx
// app/dashboard/error.tsx
"use client";

export default function Error({ error, reset }) {
  return (
    <div>
      <p>Could not load the dashboard.</p>
      <button onClick={reset}>Try again</button>
    </div>
  );
}
```

Não transforme validation/permissions comuns em 500 genérico. Modele outcomes esperados, logue failures inesperadas com contexto e não exponha stack/secrets. Ofereça retry apenas quando pode realmente funcionar.
