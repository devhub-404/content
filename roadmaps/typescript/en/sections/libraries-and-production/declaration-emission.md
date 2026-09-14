# Declaration Emission

Library builds can emit `.d.ts` files from TypeScript source with `declaration`. Declaration maps can connect published type definitions back to source for editor navigation. `emitDeclarationOnly` is useful when another tool emits the JavaScript but TypeScript still owns the public type artifacts.

```ts
{
  "compilerOptions": {
    "declaration": true,
    "declarationMap": true,
    "emitDeclarationOnly": true,
    "outDir": "./dist"
  }
}
```

Inspect the generated declarations as a consumer would. Inferred private implementation details can leak into public signatures, dependencies can become required type imports, and inaccessible internal names can make output unusable. Stable explicit annotations on exported boundaries often produce cleaner and more predictable declarations.
