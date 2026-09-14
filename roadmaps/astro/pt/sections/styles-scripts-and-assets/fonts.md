# Fonts

Astro moderno inclui tooling built-in de fonts para descrever/servir fonts com CSS e asset handling gerados. Config depende de sources locais/providers, mas objetivo é integrar font loading ao pipeline otimizado do build.

```astro
---
import { Font } from "astro:assets";
---

<Font cssVariable="--font-brand" />
<style>
  h1 { font-family: var(--font-brand), sans-serif; }
</style>
```

Typography ainda segue regras de web-font performance: limite families/weights, use fallbacks bons, evite texto invisível longo e confira licensing. Framework gera URLs/CSS, mas não decide quais fonts o design realmente precisa.
