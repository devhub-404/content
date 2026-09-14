# Core Web Vitals and Navigation Performance

Next.js optimizes routing, code splitting, prefetching, images, fonts, and server rendering, but real user performance still depends on application data, third-party code, caching, layout, and device/network conditions. Measure Core Web Vitals from real users when possible.

```tsx
import { useReportWebVitals } from "next/web-vitals";

export function WebVitals() {
  useReportWebVitals(metric => {
    sendToAnalytics(metric);
  });
  return null;
}
```

Next.js 16.3 emphasizes instant navigation and partial prefetching, but fast transitions require route shells and data boundaries that can respond promptly. Profile the slow navigation or interaction itself, then decide whether the bottleneck is server work, cache misses, client JavaScript, images, or network latency.
