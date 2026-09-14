# Error y Not-found Boundaries

Las conventions `error`, `not-found` y `global-error` ofrecen fallback por scopes. `notFound()` expresa un resource ausente esperado, mientras Error Boundaries capturan failures inesperados de rendering.

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

No conviertas validation/permissions normales en 500 genérico. Modela outcomes esperados, registra failures inesperados con contexto y no expongas stack/secrets. Ofrece retry solo cuando puede funcionar realmente.
