# Astro Config and Integrations

`astro.config.mjs` controls build, server, routing, image, Markdown, security, and integration behavior. Official and community integrations add support for UI frameworks, MDX, adapters, sitemaps, and other features through a defined Astro hook system.

```astro
import { defineConfig } from "astro/config";
import react from "@astrojs/react";

export default defineConfig({
  integrations: [react()],
  output: "static"
});
```

Start with a small config and add settings only when the project requires them. Configuration is part of the build contract, so keep environment-specific values explicit and versioned. Prefer an integration's documented API over patching Vite internals unless you truly need lower-level control.
