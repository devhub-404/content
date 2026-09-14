# Transitions y Deferred Values

Las transitions coordinan updates de menor prioridad que pueden disparar async/expensive work, mientras `createDeferred` crea un valor que puede retrasarse respecto a una source rápida. Ayudan a conservar interacción responsiva mientras la UI lenta se actualiza.

```tsx
const [pending, start] = useTransition();

function selectTab(id) {
  start(() => setTab(id));
}

const deferredQuery = createDeferred(query);
```

No vuelven gratis los algorithms costosos. Úsalos cuando el producto se beneficie de conservar contenido anterior o input responsivo, luego perfila la computation/request real. El feedback de loading/stale state debe seguir siendo comprensible.
