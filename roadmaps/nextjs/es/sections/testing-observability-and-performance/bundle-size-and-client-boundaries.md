# Bundle Size y Client Boundaries

Los Server Components mantienen implementation/dependencies server-only fuera del browser, mientras cada `use client` arrastra el client dependency graph. Bundle optimization empieza en arquitectura antes de manual code splitting.

```tsx
// Keep heavy server-only dependencies out of client modules.
import "server-only";
import { expensivePdfLibrary } from "pdf-library";

export async function createInvoicePdf() {
  return expensivePdfLibrary.render(...);
}
```

Inspecciona bundles cuando performance indique un problema, mueve libraries innecesarias a server, lazy-load features opcionales y elimina duplicates. No sacrifiques interacción útil solo para reducir un número pequeño de bundle.
