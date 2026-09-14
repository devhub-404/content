# Declaration Files (`.d.ts`)

Arquivo `.d.ts` contém declarações de tipos sem implementação JavaScript. Ele permite ao TypeScript compreender biblioteca implementada em outro lugar e é o artefato de tipos normalmente publicado por bibliotecas TypeScript para consumidores.

```ts
// index.d.ts
export interface User {
  id: string;
  name: string;
}

export function loadUser(id: string): Promise<User>;
```

Declaration files devem descrever fielmente a API de runtime real. Podem declarar módulos, globals, classes, funções, interfaces e augmentations, mas não criam esses valores em runtime. Ao publicar biblioteca, gere declarations a partir do source quando possível para manter implementação e tipos públicos sincronizados.
