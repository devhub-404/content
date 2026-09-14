# Adapters e Deployment

Static output pode ser hospedado quase em qualquer static host. On-demand rendering precisa adapter/runtime integration que converta server build para request model da plataforma, como Node, Cloudflare, Netlify ou Vercel.

```astro
import { defineConfig } from "astro/config";
import cloudflare from "@astrojs/cloudflare";

export default defineConfig({
  output: "server",
  adapter: cloudflare()
});
```

Deployment faz parte do runtime contract. Confira APIs, filesystem, streaming, image services, sessions, env vars e caching no target. Teste production build/adaptor em preview em vez de assumir comportamento do dev server.
