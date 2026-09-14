# Core Web Vitals e Navigation Performance

Next otimiza routing, splitting, prefetch, images, fonts e server rendering, mas real performance depende de data, third-party code, cache, layout e device/network. Meça Core Web Vitals reais quando possível.

```tsx
import { useReportWebVitals } from "next/web-vitals";

export function WebVitals() {
  useReportWebVitals(metric => {
    sendToAnalytics(metric);
  });
  return null;
}
```

Next 16.3 enfatiza instant navigation/partial prefetching, mas transitions rápidas exigem route shells/data boundaries responsivos. Profile interação lenta e identifique server work, cache miss, client JS, image ou network.
