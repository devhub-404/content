# Third-party Client Components

Un third-party component con React client-only puede necesitar un wrapper local `use client` cuando el package no expone una boundary correcta. Los Server Components pueden importar el wrapper sin volver toda la route client-rendered.

```tsx
"use client";

export { Carousel } from "acme-carousel";
```

Mantén wrappers pequeños y documenta el motivo. Package upgrades pueden añadir directives o cambiar assumptions. Si la library accede a browser globals durante module evaluation, puede requerir dynamic loading además de client directive.
