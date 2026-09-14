# Resolução de Módulos

TypeScript precisa resolver import para type checking e, conforme o projeto, compreender o que o runtime carregará. Configurações de module resolution modelam ambientes como Node moderno ou bundlers. Elas não reescrevem magicamente regras do runtime salvo se uma ferramenta de emissão fizer isso explicitamente.

```ts
// source
import { parse } from "./parse.js";
import type { Config } from "my-package";

// tsconfig.json varies by runtime/bundler:
// module + moduleResolution must match the environment.
```

Escolha `module` e `moduleResolution` conforme runtime/build real, não tutorial antigo. Package exports do Node, extensões, campo `type`, conditional exports e comportamento do bundler afetam resolução. TypeScript 6.0 deprecia modos antigos como `node10` e `classic`, então projetos novos devem começar com settings atuais do ambiente.
