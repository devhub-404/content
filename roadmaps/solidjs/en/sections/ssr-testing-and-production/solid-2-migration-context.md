# Solid 2.0 RC and Migration Context

Solid 2.0 reached release-candidate development in 2026 with substantial work around async reactivity and framework behavior, but RC packages are pre-releases rather than the stable baseline. Production learning material should distinguish stable Solid 1.x contracts from upcoming migration details.

```tsx
// Keep production dependencies on the stable line unless
// your project has explicitly chosen the Solid 2 migration path.

import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);
```

When adopting 2.0, read the official migration and release notes for the exact RC or final version instead of assuming all 1.x behavior carries forward unchanged. Upgrade Solid, router, and SolidStart deliberately because ecosystem packages may have coordinated compatibility requirements.
