# Next Config e Runtime Choices

`next.config.ts` controla build output, images, redirects, cache components, experimental features, packages e platform integration. A maioria dos apps deve manter config pequena e deixar conventions do App Router cuidarem do comportamento comum.

```tsx
import type { NextConfig } from "next";

const nextConfig: NextConfig = {
  reactStrictMode: true,
  cacheComponents: true
};

export default nextConfig;
```

Runtime capabilities importam mais que rótulos. Server Components/Route Handlers normalmente usam runtime server compatível com Node, enquanto targets específicos podem restringir APIs. Escolha conforme target real e verifique em production build.
