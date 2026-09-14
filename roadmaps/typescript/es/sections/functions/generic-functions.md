# Funciones genéricas

Una función genérica introduce type parameters para conservar relaciones entre inputs y outputs. En `first<T>`, el tipo de los elementos de entrada determina el posible retorno. TypeScript suele inferir `T` a partir de los argumentos.

```ts
function first<T>(items: readonly T[]): T | undefined {
  return items[0];
}

const name = first(["Mina", "Ada"]);
const number = first([10, 20]);
```

Usa generics cuando quieras preservar información que se perdería con `any` o overloads repetidos. Un type parameter que aparece una sola vez muchas veces no expresa ninguna relación útil. Los buenos generics conectan tipos; no solo hacen que una firma parezca abstracta.
