# Lazy Components

`lazy` carga un module de component solo cuando se vuelve necesario. El lazy component se integra con Suspense, permitiendo fallback mientras se fetch/inicializa el code chunk.

```tsx
const Settings = lazy(() => import("./Settings"));

<Suspense fallback={<p>Loading…</p>}>
  <Settings />
</Suspense>
```

Divide código en feature/route boundaries significativas en vez de convertir cada component pequeño en una request. Los bundlers modernos ya hacen tree shaking/splitting. Mide el trade-off entre initial bundle, request count y navigation latency.
