# `untrack`, `on` y Control Explícito de Dependencies

Solid normalmente descubre dependencies automáticamente, pero `on` puede hacer que una computation reaccione a sources explícitas y `untrack` lee un valor reactivo sin suscribir el tracking scope actual. Son herramientas precisas de dependency control.

```tsx
createEffect(on(userId, id => {
  const themeNow = untrack(theme);
  console.log("user changed", id, themeNow);
}));
```

No las uses para silenciar reactividad que no entiendes. Si un valor realmente afecta el resultado, normalmente debe ser dependency. `untrack` sirve para lecturas incidentales como logging/contexto puntual; `on` cuando la propia boundary forma parte del diseño.
