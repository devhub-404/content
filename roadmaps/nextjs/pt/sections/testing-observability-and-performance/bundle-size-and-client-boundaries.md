# Bundle Size e Client Boundaries

Server Components mantêm implementation/dependencies server-only fora do browser, enquanto cada `use client` puxa client dependency graph. Bundle optimization começa na arquitetura antes de manual code splitting.

```tsx
// Keep heavy server-only dependencies out of client modules.
import "server-only";
import { expensivePdfLibrary } from "pdf-library";

export async function createInvoicePdf() {
  return expensivePdfLibrary.render(...);
}
```

Inspecione bundles quando performance indicar problema, mova libraries desnecessárias para server, lazy-load features opcionais e remova duplicates. Não sacrifique interação útil apenas para reduzir número pequeno de bundle.
