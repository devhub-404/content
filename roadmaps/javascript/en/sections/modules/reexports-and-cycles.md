# Re-exports and Cycles

Re-exports let a feature or package expose a deliberate public surface while keeping internal files private to its implementation. `export *` can be concise but makes the public names less obvious and may create conflicts when several source modules export the same name.

```js
// public-api.js
export { createUser } from "./create-user.js";
export { validateUser } from "./validate-user.js";
export { UserError } from "./errors.js";
```

ES modules define circular dependencies, but tightly coupled cycles can be difficult because imported bindings may exist before their defining module has finished initialization. Prefer extracting a lower-level shared responsibility instead of creating modules that require each other's initialized state. A stable public module boundary should allow internal file structure to change without breaking consumers.
