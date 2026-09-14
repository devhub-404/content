# View Transitions e Client Router

Astro pode melhorar navigation com client router/View Transition mantendo route content baseado em server-rendered documents. Transition directives conectam elements entre navigations e scripts respondem a lifecycle events do Astro.

```astro
---
import { ClientRouter } from "astro:transitions";
---
<head>
  <ClientRouter />
</head>

<h1 transition:name="page-title">Docs</h1>
```

Client navigation muda assumptions de scripts/lifecycle, então teste código dependente de `DOMContentLoaded`. Respeite reduced motion e preserve focus/scroll/history. Use transitions para continuity, não para esconder route lenta.
