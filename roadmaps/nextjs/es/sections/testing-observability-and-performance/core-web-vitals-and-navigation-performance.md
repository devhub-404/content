# Core Web Vitals y Navigation Performance

Next optimiza routing, splitting, prefetch, images, fonts y server rendering, pero el real performance depende de data, third-party code, cache, layout y device/network. Mide Core Web Vitals reales cuando sea posible.

```tsx
import { useReportWebVitals } from "next/web-vitals";

export function WebVitals() {
  useReportWebVitals(metric => {
    sendToAnalytics(metric);
  });
  return null;
}
```

Next 16.3 enfatiza instant navigation/partial prefetching, pero transitions rápidas exigen route shells/data boundaries responsivos. Perfila la interacción lenta e identifica server work, cache miss, client JS, image o network.
