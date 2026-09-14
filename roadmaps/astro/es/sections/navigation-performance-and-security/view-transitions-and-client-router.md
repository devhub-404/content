# View Transitions y Client Router

Astro puede mejorar navigation con client router/View Transition manteniendo route content basado en server-rendered documents. Transition directives conectan elements entre navigations y scripts responden a lifecycle events de Astro.

```astro
---
import { ClientRouter } from "astro:transitions";
---
<head>
  <ClientRouter />
</head>

<h1 transition:name="page-title">Docs</h1>
```

Client navigation cambia assumptions de scripts/lifecycle, así que prueba código dependiente de `DOMContentLoaded`. Respeta reduced motion y conserva focus/scroll/history. Usa transitions para continuity, no para ocultar una route lenta.
