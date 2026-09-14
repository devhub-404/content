# DevTools e Debugging Reativo

Solid DevTools e logging focado ajudam a ver component ownership, signals, computations e updates. Como component não rerenderiza no sentido React, debugging deve seguir reactive graph: qual source mudou, qual computation assinou e qual DOM expression atualizou.

```tsx
createEffect(() => {
  console.debug({
    query: query(),
    resultCount: filtered().length
  });
});
```

Não adicione effects permanentes só para inspecionar state; remova diagnostics temporários. Para performance, olhe computations caras, list reconciliation, async waterfalls e external work, não número de chamadas de component.
