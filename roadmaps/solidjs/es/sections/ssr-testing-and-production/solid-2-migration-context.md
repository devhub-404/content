# Solid 2.0 RC y Contexto de Migración

Solid 2.0 llegó a release candidate en 2026 con cambios importantes en async reactivity/framework behavior, pero un RC es pre-release, no baseline estable. El material de producción debe distinguir contratos Solid 1.x de detalles de migración futura.

```tsx
// Keep production dependencies on the stable line unless
// your project has explicitly chosen the Solid 2 migration path.

import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);
```

Al adoptar 2.0, lee migration/release notes de la versión exacta en vez de suponer compatibilidad total. Actualiza Solid, router y SolidStart deliberadamente porque ecosystem packages pueden tener requirements coordinados.
