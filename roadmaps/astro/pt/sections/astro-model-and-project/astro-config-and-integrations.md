# Astro Config e Integrations

`astro.config.mjs` controla build, server, routing, images, Markdown, security e integrations. Integrations oficiais/comunitárias adicionam UI frameworks, MDX, adapters, sitemaps e outras features por hooks definidos do Astro.

```astro
import { defineConfig } from "astro/config";
import react from "@astrojs/react";

export default defineConfig({
  integrations: [react()],
  output: "static"
});
```

Comece com config pequena e adicione settings quando houver necessidade. Configuração faz parte do build contract, então mantenha values por environment explícitos/versionados. Prefira API documentada da integration a patching de internals do Vite.
