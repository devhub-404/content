# Fonts

Modern Astro includes built-in font tooling for describing and serving project fonts with generated CSS and asset handling. The exact configuration depends on local or provider sources, but the goal is to make font loading part of the same optimized build pipeline as other assets.

```astro
---
import { Font } from "astro:assets";
---

<Font cssVariable="--font-brand" />
<style>
  h1 { font-family: var(--font-brand), sans-serif; }
</style>
```

Typography still follows web-font performance rules: limit unnecessary families and weights, use sensible fallbacks, avoid invisible text for long periods, and verify licensing. A framework can generate URLs and CSS, but it cannot decide which fonts the design actually needs.
