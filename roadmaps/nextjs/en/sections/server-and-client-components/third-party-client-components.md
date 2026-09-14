# Third-party Client Components

A third-party component that uses client-only React features may need to be wrapped in a local `use client` module when the package itself does not expose an appropriate boundary. Server Components can then import the wrapper without making the entire parent route client-rendered.

```tsx
"use client";

export { Carousel } from "acme-carousel";
```

Keep wrappers small and document why they exist. Package upgrades may add proper client directives or change runtime assumptions. If a library accesses browser globals at module evaluation time, it may require dynamic loading or other integration work beyond simply placing a client directive around it.
