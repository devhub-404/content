# Usando React, Vue, Solid y Otros Frameworks

Las integrations permiten components de UI frameworks dentro de `.astro`. Sin client directive pueden renderizar HTML en server sin hydration runtime; con `client:*` se vuelven client islands interactivas.

```astro
---
import ReactCard from "../components/ReactCard.jsx";
import SolidCounter from "../components/SolidCounter.tsx";
---

<ReactCard title="Static render" />
<SolidCounter client:visible />
```

Usa un framework de forma consistente para interactive state relacionado salvo una razón fuerte. Islands de runtimes distintos no comparten memory state casualmente. Usa URL, DOM events, web storage o un store deliberado para coordinar.
