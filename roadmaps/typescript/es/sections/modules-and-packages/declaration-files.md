# Declaration files (`.d.ts`)

Un archivo `.d.ts` contiene declaraciones de tipos sin la implementación JavaScript. Permite que TypeScript comprenda una biblioteca escrita o ejecutada en otro lugar y es el artefacto normal que una biblioteca TypeScript publica para sus consumidores.

```ts
// index.d.ts
export interface User {
  id: string;
  name: string;
}

export function loadUser(id: string): Promise<User>;
```

Las declarations deben describir fielmente la API de runtime; no crean valores. Si publicas una biblioteca, genera `.d.ts` desde el source cuando sea posible y revisa el resultado para evitar que detalles internos o nombres inaccesibles se filtren en el contrato público.
