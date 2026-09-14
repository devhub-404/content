# Imports y exports solo de tipo

`import type` y `export type` indican que un binding existe únicamente para el checker y no debe crear dependencia runtime. También puedes usar el modifier `type` inline para mezclar valores y tipos en una misma declaración.

```ts
import type { User } from "./types.js";
import { createUser, type UserOptions } from "./users.js";

export type { User };
export { createUser };
```

Un nombre puede existir en el mundo de tipos, de valores o en ambos. Classes existen en ambos; interfaces solo como tipos. Escribe imports que reflejen si el JavaScript runtime necesita realmente esa dependencia, especialmente con configuraciones modernas que preservan la sintaxis de módulos.
