# Resolución de módulos

TypeScript necesita resolver cada import para comprobar tipos y modelar lo que hará el runtime. Los settings de module resolution deben corresponder al entorno real, como Node moderno o un bundler, y no reescriben mágicamente las reglas del host salvo que otra herramienta haga esa transformación.

```ts
// source
import { parse } from "./parse.js";
import type { Config } from "my-package";

// tsconfig.json varies by runtime/bundler:
// module + moduleResolution must match the environment.
```

Extensiones, package exports, campo `type`, conditional exports y aliases influyen en la resolución. No copies un setting antiguo por costumbre. Los proyectos nuevos deben usar modos actuales adecuados al runtime en lugar de `classic` o configuraciones legacy.
