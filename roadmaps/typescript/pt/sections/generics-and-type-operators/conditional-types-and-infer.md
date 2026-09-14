# Conditional Types e `infer`

Conditional type escolhe um tipo ou outro conforme assignability: `T extends U ? X : Y`. Com input genérico, conditional types codificam relações dependentes do tipo fornecido. `infer` introduz type variable a partir de padrão, como extrair elemento de array ou retorno de função.

```ts
type ElementType<T> =
  T extends readonly (infer U)[]
    ? U
    : T;

type A = ElementType<string[]>; // string
type B = ElementType<number>;   // number
```

Conditional types podem distribuir sobre type parameters union, o que é poderoso mas às vezes surpreendente. Envolva o tipo verificado em tuple quando quiser impedir distributividade. Use conditional types para relações reutilizáveis, não para construir programas de compile time ilegíveis quando tipo explícito simples comunicaria melhor a API.
