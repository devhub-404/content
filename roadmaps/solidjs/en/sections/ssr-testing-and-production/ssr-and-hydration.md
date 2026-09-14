# SSR and Hydration

Solid can render HTML on the server and hydrate it in the browser so fine-grained client reactivity attaches to server-generated markup. Streaming APIs and framework integrations add async rendering and routing around the same core model.

```tsx
import { renderToString } from "solid-js/web";

const html = renderToString(() => <App />);
```

Server and client output must agree during hydration. Browser-only APIs, random values, time, or shared module state can create mismatches or request leakage. In full applications, a framework such as SolidStart normally owns the SSR pipeline, serialization, routing, and deployment adapter.
