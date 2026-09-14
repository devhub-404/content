# Links, Prefetching e Navigation

`<Link>` fornece semantics acessíveis, client navigation e prefetch do framework. Next pode buscar route payload antes do click para shared layouts permanecerem mounted e próxima route aparecer rápido. Behavior depende de structure/cache/rendering.

```tsx
import Link from "next/link";

<Link href="/dashboard">Dashboard</Link>
```

Use links reais para navigation e buttons para actions. Não prefetch destinations enormes/raros cegamente. Next 16.3 adiciona instant navigation/partial prefetching, mas route rápida ainda depende de boundaries e data sensatos.
