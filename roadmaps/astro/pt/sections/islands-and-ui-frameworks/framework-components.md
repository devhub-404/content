# Usando React, Vue, Solid e Outros Frameworks

Integrations permitem components de UI frameworks dentro de `.astro`. Sem client directive eles podem renderizar HTML no server sem hydration runtime; com `client:*` viram client islands interativas.

```astro
---
import ReactCard from "../components/ReactCard.jsx";
import SolidCounter from "../components/SolidCounter.tsx";
---

<ReactCard title="Static render" />
<SolidCounter client:visible />
```

Use um framework consistentemente para interactive state relacionado salvo motivo forte. Islands de runtimes diferentes não compartilham memory state casualmente. Use URL, DOM events, web storage ou store deliberado para coordenação.
