# Type-only Imports and Exports

`import type` and `export type` state that a binding exists only for type checking and should not become a runtime import/export. Inline `type` modifiers can mix value and type imports in one declaration. This clarity is important under modern module-preservation settings.

```ts
import type { User } from "./types.js";
import { createUser, type UserOptions } from "./users.js";

export type { User };
export { createUser };
```

A name can exist in the type world, value world, or both. Classes are both; interfaces are type-only. Avoid relying on older compiler behavior that silently removes imports based on usage in ways your runtime loader cannot understand. Write syntax that accurately reflects whether runtime JavaScript needs the dependency.
