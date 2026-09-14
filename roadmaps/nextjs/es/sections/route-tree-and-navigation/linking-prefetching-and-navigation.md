# Links, Prefetching y Navigation

`<Link>` ofrece semántica accesible, client navigation y prefetch del framework. Next puede obtener route payload antes del click para que shared layouts sigan mounted y la siguiente route aparezca rápido. El comportamiento depende de structure/cache/rendering.

```tsx
import Link from "next/link";

<Link href="/dashboard">Dashboard</Link>
```

Usa links reales para navigation y buttons para actions. No prefetch destinos enormes/raros ciegamente. Next 16.3 añade instant navigation/partial prefetching, pero una route rápida aún depende de boundaries y data sensatos.
