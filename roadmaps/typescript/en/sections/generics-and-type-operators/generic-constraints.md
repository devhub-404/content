# Generic Constraints

A generic constraint limits which types can be substituted for a type parameter while preserving information about the specific input. `T extends { length: number }` says callers may pass any type with a numeric length, and inside the function TypeScript knows that property is available.

```ts
function getLength<T extends { length: number }>(value: T) {
  return value.length;
}

getLength("hello");
getLength([1, 2, 3]);
```

Constraints should express the minimum capability the implementation requires. Over-constraining a generic makes it less reusable and can destroy inference. If a function only needs one property, constrain that property rather than requiring a large interface simply because current callers happen to have one.
