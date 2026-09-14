# Third-party Client Components

Third-party component com client-only React pode precisar wrapper local `use client` quando package não expõe boundary correta. Server Components então importam wrapper sem tornar route inteira client-rendered.

```tsx
"use client";

export { Carousel } from "acme-carousel";
```

Mantenha wrappers pequenos e documente motivo. Package upgrades podem adicionar directives ou mudar assumptions. Se library acessa browser globals no module evaluation, pode exigir dynamic loading além de client directive.
