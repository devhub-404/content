# Astro Config e Integrations

`astro.config.mjs` controla build, server, routing, images, Markdown, security e integrations. Integrations oficiales/comunitarias añaden UI frameworks, MDX, adapters, sitemaps y otras features mediante hooks definidos de Astro.

```astro
import { defineConfig } from "astro/config";
import react from "@astrojs/react";

export default defineConfig({
  integrations: [react()],
  output: "static"
});
```

Empieza con una config pequeña y añade settings cuando sean necesarios. La configuración forma parte del build contract, así que mantén values por environment explícitos/versionados. Prefiere la API documentada de una integration a parchear internals de Vite.
