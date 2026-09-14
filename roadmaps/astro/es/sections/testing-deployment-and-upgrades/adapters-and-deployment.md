# Adapters y Deployment

El static output puede alojarse en casi cualquier static host. On-demand rendering necesita adapter/runtime integration que convierta el server build al request model de la plataforma, como Node, Cloudflare, Netlify o Vercel.

```astro
import { defineConfig } from "astro/config";
import cloudflare from "@astrojs/cloudflare";

export default defineConfig({
  output: "server",
  adapter: cloudflare()
});
```

Deployment forma parte del runtime contract. Comprueba APIs, filesystem, streaming, image services, sessions, env vars y caching en el target. Prueba production build/adapter en preview en vez de asumir el comportamiento del dev server.
