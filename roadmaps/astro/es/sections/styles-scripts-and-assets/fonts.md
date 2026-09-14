# Fonts

Astro moderno incluye tooling built-in de fonts para describir/servir fonts con CSS y asset handling generados. La config depende de sources locales/providers, pero el objetivo es integrar font loading con el pipeline optimizado del build.

```astro
---
import { Font } from "astro:assets";
---

<Font cssVariable="--font-brand" />
<style>
  h1 { font-family: var(--font-brand), sans-serif; }
</style>
```

Typography sigue las reglas de web-font performance: limita families/weights, usa buenos fallbacks, evita texto invisible durante mucho tiempo y revisa licensing. El framework genera URLs/CSS, pero no decide qué fonts necesita realmente el diseño.
