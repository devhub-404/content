# Module Resolution

TypeScript must resolve an import both for type checking and, depending on the project, for understanding what the runtime will load. Module resolution settings model environments such as modern Node.js or bundlers. They do not magically rewrite the runtime's rules unless an emitting tool explicitly does so.

```ts
// source
import { parse } from "./parse.js";
import type { Config } from "my-package";

// tsconfig.json varies by runtime/bundler:
// module + moduleResolution must match the environment.
```

Choose `module` and `moduleResolution` according to the actual runtime/build system, not from an old tutorial. Modern Node package exports, file extensions, package `type`, conditional exports, and bundler behavior all affect resolution. TypeScript 6.0 deprecates older resolution modes such as `node10` and `classic`, so new projects should start from current environment-specific settings.
