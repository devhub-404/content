# `keyof` e Indexed Access Types

`keyof T` produz union das property keys conhecidas no tipo. Indexed access type `T[K]` recupera o tipo da propriedade em uma ou mais chaves. Juntos permitem que APIs genéricas preservem relação entre chave selecionada e valor retornado.

```ts
type User = {
  id: string;
  name: string;
  active: boolean;
};

type UserKey = keyof User;       // "id" | "name" | "active"
type UserName = User["name"];    // string

function get<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
```

Esses operadores funcionam somente no sistema de tipos; `keyof` não é reflection de runtime. Index signatures afetam o tipo de chave resultante por causa da coerção de chaves de objetos JavaScript. Use chaves constrained em vez de `string` amplo quando API deve aceitar apenas propriedades realmente existentes.
