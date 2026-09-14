# Using React, Vue, Solid, and Other Framework Components

Astro integrations allow components from supported UI frameworks to render inside `.astro` templates. Without a client directive they can render to HTML on the server and ship no hydration runtime; adding `client:*` turns them into interactive client islands.

```astro
---
import ReactCard from "../components/ReactCard.jsx";
import SolidCounter from "../components/SolidCounter.tsx";
---

<ReactCard title="Static render" />
<SolidCounter client:visible />
```

Use one framework consistently for related interactive state unless there is a strong migration or library reason to mix several. Framework islands cannot casually share in-memory state across separate runtimes. Use URL, DOM events, web storage, or a deliberate cross-island store when coordination is required.
