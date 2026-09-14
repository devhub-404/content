# DevTools y Debugging Reactivo

Solid DevTools y logging enfocado ayudan a ver component ownership, signals, computations y updates. Como un component no rerenderiza en el sentido de React, el debugging debe seguir el reactive graph: qué source cambió, qué computation se suscribió y qué DOM expression actualizó.

```tsx
createEffect(() => {
  console.debug({
    query: query(),
    resultCount: filtered().length
  });
});
```

No añadas effects permanentes solo para inspeccionar state; elimina diagnostics temporales. Para performance, mira computations costosas, list reconciliation, async waterfalls y external work, no el número de llamadas de component.
