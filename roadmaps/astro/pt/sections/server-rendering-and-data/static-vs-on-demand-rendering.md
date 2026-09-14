# Rendering Static vs On-demand

Astro pode prerender routes para arquivos estáticos ou renderizar on demand por server adapter. Static output é simples/cache-friendly; on-demand suporta per-request data, sessions, auth e responses desconhecidas no build.

```astro
import { defineConfig } from "astro/config";
import node from "@astrojs/node";

export default defineConfig({
  output: "server",
  adapter: node({ mode: "standalone" })
});
```

Escolha rendering por route/freshness, não por moda. Static pages ainda podem ter client islands e server pages podem cachear. Adapter conecta server output do Astro ao runtime da plataforma.
