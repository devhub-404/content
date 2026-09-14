# SSR e Hydration

Solid pode renderizar HTML no server e fazer hydration no browser, conectando fine-grained reactivity ao markup gerado. Streaming APIs/framework integrations adicionam async rendering/routing ao mesmo modelo.

```tsx
import { renderToString } from "solid-js/web";

const html = renderToString(() => <App />);
```

Server e client precisam concordar no hydration. Browser-only APIs, random/time ou shared module state podem criar mismatch/leak entre requests. Em full apps, SolidStart normalmente controla SSR, serialization, routing e deployment.
