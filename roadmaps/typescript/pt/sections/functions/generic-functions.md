# Funções Genéricas

Função genérica introduz type parameters que descrevem relações entre inputs e outputs. Em `first<T>`, o tipo dos elementos de entrada determina o retorno. TypeScript normalmente infere `T` pelos argumentos, então callers não precisam escrever type arguments explícitos.

```ts
function first<T>(items: readonly T[]): T | undefined {
  return items[0];
}

const name = first(["Mina", "Ada"]);
const number = first([10, 20]);
```

Use generics quando valores compartilham relação de tipos que seria perdida com `any` ou overloads repetidos. Um type parameter que aparece apenas uma vez frequentemente não adiciona relação útil e pode ser substituído por `unknown` ou tipo concreto. Bons generics preservam informação em vez de apenas deixar assinatura abstrata.
