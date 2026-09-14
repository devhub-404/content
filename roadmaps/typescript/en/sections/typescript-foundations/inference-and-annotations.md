# Inference and Type Annotations

Type inference lets TypeScript derive types from initializers, control flow, return expressions, contextual expectations, and generic relationships. You do not need to annotate every variable. In fact, unnecessary annotations can repeat information and make refactoring noisier.

```ts
const count = 3;           // inferred as 3
let total = 0;             // inferred as number

function add(a: number, b: number) {
  return a + b;            // return type inferred as number
}
```

Annotations are most useful at boundaries: public function parameters, exported APIs, intentionally broad variables, or places where inference would choose a type narrower or wider than your design. Return types are often inferable, but explicit annotations on exported functions can document a stable contract and catch accidental API changes.
