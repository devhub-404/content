# SSR y Hydration

Solid puede renderizar HTML en server e hidratarlo en browser, conectando fine-grained reactivity al markup generado. Streaming APIs/framework integrations añaden async rendering/routing al mismo modelo.

```tsx
import { renderToString } from "solid-js/web";

const html = renderToString(() => <App />);
```

Server y client deben coincidir durante hydration. Browser-only APIs, random/time o shared module state pueden crear mismatch/leak entre requests. En full apps, SolidStart normalmente controla SSR, serialization, routing y deployment.
