# View Transitions and Client Router

Astro can enhance page navigation with a client router and View Transition integration while keeping route content based on server-rendered documents. Transition directives can connect elements across navigations and scripts can respond to Astro navigation lifecycle events.

```astro
---
import { ClientRouter } from "astro:transitions";
---
<head>
  <ClientRouter />
</head>

<h1 transition:name="page-title">Docs</h1>
```

Client-side navigation changes script and lifecycle assumptions, so test pages that depend on one-time `DOMContentLoaded` setup. Respect reduced-motion preferences and maintain focus, scroll, and history behavior. Use transitions to improve continuity, not to disguise slow route generation.
