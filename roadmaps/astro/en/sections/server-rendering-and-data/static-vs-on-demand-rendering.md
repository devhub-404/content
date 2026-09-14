# Static vs On-demand Rendering

Astro can prerender routes to static files or render them on demand through a server adapter. Static output is simple and cache-friendly, while on-demand rendering supports per-request data, sessions, authentication, and dynamic responses that cannot be known at build time.

```astro
import { defineConfig } from "astro/config";
import node from "@astrojs/node";

export default defineConfig({
  output: "server",
  adapter: node({ mode: "standalone" })
});
```

Choose rendering per route and data freshness, not because one mode sounds more modern. Static pages can still contain client islands, and server-rendered pages can still cache aggressively. An adapter connects Astro's server output to the runtime used by the deployment platform.
