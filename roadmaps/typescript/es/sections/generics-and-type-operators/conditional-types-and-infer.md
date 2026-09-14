# Conditional types e `infer`

Un conditional type elige entre dos tipos mediante `T extends U ? X : Y`. Cuando el input es genérico, puede expresar relaciones dependientes del tipo suministrado. `infer` introduce un type variable a partir de un patrón, como el elemento de un array o el retorno de una función.

```ts
type ElementType<T> =
  T extends readonly (infer U)[]
    ? U
    : T;

type A = ElementType<string[]>; // string
type B = ElementType<number>;   // number
```

Los conditional types pueden distribuir sobre unions y eso es potente pero a veces sorprendente. Úsalos para relaciones reutilizables, no para construir programas de tipos opacos cuando una definición más explícita comunicaría mejor la API.
