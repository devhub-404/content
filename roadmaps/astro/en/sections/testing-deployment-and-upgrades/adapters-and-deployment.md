# Adapters and Deployment

Static Astro output can be hosted on almost any static host. On-demand rendering needs an adapter or supported runtime integration that turns Astro's server build into the target platform's request model, such as Node, Cloudflare, Netlify, or Vercel.

```astro
import { defineConfig } from "astro/config";
import cloudflare from "@astrojs/cloudflare";

export default defineConfig({
  output: "server",
  adapter: cloudflare()
});
```

Deployment is part of the runtime contract. Check supported APIs, filesystem access, streaming, image services, sessions, environment variables, and caching behavior for the target. Test the adapter's production build locally or in preview instead of assuming dev-server behavior exactly matches the platform.
