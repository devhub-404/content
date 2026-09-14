# Lazy Components

`lazy` carrega module de component apenas quando necessário. Lazy component integra com Suspense, permitindo fallback enquanto code chunk é fetched/inicializado.

```tsx
const Settings = lazy(() => import("./Settings"));

<Suspense fallback={<p>Loading…</p>}>
  <Settings />
</Suspense>
```

Divida code em feature/route boundaries significativas em vez de transformar cada component pequeno em request. Bundlers modernos já fazem tree shaking/splitting. Meça trade-off entre initial bundle, request count e navigation latency.
