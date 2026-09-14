# Rendering Static vs On-demand

Astro puede prerender routes a archivos estáticos o renderizarlas on demand mediante un server adapter. Static output es simple/cache-friendly; on-demand soporta per-request data, sessions, auth y responses desconocidas en build.

```astro
import { defineConfig } from "astro/config";
import node from "@astrojs/node";

export default defineConfig({
  output: "server",
  adapter: node({ mode: "standalone" })
});
```

Elige rendering por route/freshness, no por moda. Static pages aún pueden tener client islands y server pages pueden cachear. Un adapter conecta el server output de Astro con el runtime de la plataforma.
