# Next Config y Runtime Choices

`next.config.ts` controla build output, images, redirects, cache components, experimental features, packages y platform integration. La mayoría de apps debería mantener config pequeña y dejar que las conventions del App Router resuelvan el comportamiento normal.

```tsx
import type { NextConfig } from "next";

const nextConfig: NextConfig = {
  reactStrictMode: true,
  cacheComponents: true
};

export default nextConfig;
```

Las runtime capabilities importan más que las etiquetas. Server Components/Route Handlers normalmente usan un runtime server compatible con Node, mientras targets específicos pueden restringir APIs. Elige según el target real y verifícalo en production build.
