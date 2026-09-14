# Next Config and Runtime Choices

`next.config.ts` controls framework behavior such as build output, images, redirects, cache components, experimental features, package handling, and platform integration. Most applications should keep configuration small and let App Router conventions handle ordinary behavior.

```tsx
import type { NextConfig } from "next";

const nextConfig: NextConfig = {
  reactStrictMode: true,
  cacheComponents: true
};

export default nextConfig;
```

Runtime capabilities matter more than labels. Server Components and Route Handlers commonly run on Node.js-compatible server runtimes, while platform-specific runtimes may restrict Node APIs or deployment behavior. Pick features that match the actual target and verify them in a production build, not only the dev server.
