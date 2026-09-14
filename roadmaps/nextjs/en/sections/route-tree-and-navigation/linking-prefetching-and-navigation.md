# Linking, Prefetching, and Navigation

`<Link>` provides accessible link semantics plus client navigation and framework prefetching. Next.js can fetch route payloads before a click so shared layouts remain mounted and the next route can appear quickly. Prefetch behavior depends on route structure, cache state, and whether content is static, cached, or dynamic.

```tsx
import Link from "next/link";

<Link href="/dashboard">Dashboard</Link>
```

Use real links for navigation and buttons for actions. Do not prefetch enormous or rarely visited destinations blindly; control prefetching where bandwidth matters. Next.js 16.3 adds stronger instant-navigation and partial-prefetching tools, but a fast route still depends on sensible data and component boundaries.
