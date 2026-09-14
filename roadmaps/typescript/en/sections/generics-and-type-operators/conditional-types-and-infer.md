# Conditional Types and `infer`

A conditional type chooses one type or another according to assignability: `T extends U ? X : Y`. With a generic input, conditional types can encode relationships that depend on the supplied type. The `infer` keyword introduces a type variable from a pattern, such as extracting an array element or function return type.

```ts
type ElementType<T> =
  T extends readonly (infer U)[]
    ? U
    : T;

type A = ElementType<string[]>; // string
type B = ElementType<number>;   // number
```

Conditional types can distribute over union type parameters, which is powerful but sometimes surprising. Wrap the checked type in a tuple when you intentionally want to prevent distributivity. Use conditional types to capture reusable type relationships, not to build unreadable compile-time programs when a simpler explicit type would communicate the API better.
