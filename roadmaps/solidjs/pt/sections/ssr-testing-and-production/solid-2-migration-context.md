# Solid 2.0 RC e Contexto de Migração

Solid 2.0 chegou a release candidate em 2026 com mudanças importantes em async reactivity/framework behavior, mas RC é pre-release, não baseline estável. Material de produção deve distinguir contratos Solid 1.x de detalhes de migração futura.

```tsx
// Keep production dependencies on the stable line unless
// your project has explicitly chosen the Solid 2 migration path.

import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);
```

Ao adotar 2.0, leia migration/release notes da versão exata em vez de presumir compatibilidade total. Atualize Solid, router e SolidStart deliberadamente porque ecosystem packages podem ter requirements coordenados.
