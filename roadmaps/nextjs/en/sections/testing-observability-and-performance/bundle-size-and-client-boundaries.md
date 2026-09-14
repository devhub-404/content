# Bundle Size and Client Boundaries

Server Components keep their implementation and server-only dependencies out of the browser bundle, while every `use client` boundary pulls its client dependency graph into browser JavaScript. Bundle optimization therefore begins with architecture before manual code splitting.

```tsx
// Keep heavy server-only dependencies out of client modules.
import "server-only";
import { expensivePdfLibrary } from "pdf-library";

export async function createInvoicePdf() {
  return expensivePdfLibrary.render(...);
}
```

Inspect bundles when user performance indicates a problem, then move unnecessary libraries out of client code, lazy-load optional interactive features, and remove duplicate dependencies. Do not convert useful client interaction back to awkward server round trips solely to chase a small bundle number.
