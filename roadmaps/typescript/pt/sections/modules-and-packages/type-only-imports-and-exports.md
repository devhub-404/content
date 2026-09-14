# Imports e Exports Apenas de Tipo

`import type` e `export type` declaram que binding existe apenas para type checking e não deve virar import/export de runtime. Modifiers `type` inline misturam imports de valor e tipo na mesma declaração. Essa clareza importa com configurações modernas de preservação de módulos.

```ts
import type { User } from "./types.js";
import { createUser, type UserOptions } from "./users.js";

export type { User };
export { createUser };
```

Um nome pode existir no mundo de tipos, valores ou ambos. Classes são ambos; interfaces são apenas tipo. Evite depender de comportamento antigo do compilador que removia imports silenciosamente conforme uso de forma que o runtime loader não entende. Escreva sintaxe refletindo se JavaScript de runtime realmente precisa da dependência.
