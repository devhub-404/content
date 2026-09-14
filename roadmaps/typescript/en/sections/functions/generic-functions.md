# Generic Functions

A generic function introduces type parameters that describe relationships between inputs and outputs. In `first<T>`, the element type of the input determines the returned type. TypeScript normally infers `T` from the arguments, so callers do not need to write explicit type arguments.

```ts
function first<T>(items: readonly T[]): T | undefined {
  return items[0];
}

const name = first(["Mina", "Ada"]);
const number = first([10, 20]);
```

Use generics when values share a type relationship that would otherwise be lost with `any` or repeated overloads. A type parameter that appears only once often adds no useful relationship and may be replaceable with `unknown` or a concrete type. Good generics preserve information rather than merely making a signature look abstract.
