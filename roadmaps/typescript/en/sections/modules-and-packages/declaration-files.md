# Declaration Files (`.d.ts`)

A `.d.ts` file contains type declarations without the JavaScript implementation. It lets TypeScript understand a library implemented elsewhere, and it is the normal type artifact published by TypeScript libraries for consumers.

```ts
// index.d.ts
export interface User {
  id: string;
  name: string;
}

export function loadUser(id: string): Promise<User>;
```

Declaration files should describe the actual runtime API faithfully. They can declare modules, globals, classes, functions, interfaces, and augmentations, but they do not create those runtime values. When publishing a library, generate declarations from the source when possible so implementation and public types stay synchronized.
