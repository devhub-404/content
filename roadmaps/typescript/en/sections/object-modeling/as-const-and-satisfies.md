# `as const` and `satisfies`

`as const` asks TypeScript to keep literal values narrow and make object/array members readonly in the inferred type. It is useful for constant lookup tables, discriminant data, and tuple-like values where widening to `string` or mutable arrays would lose useful information.

```ts
const routes = {
  home: "/",
  users: "/users",
} as const;

const palette = {
  primary: "#2457d6",
  danger: "#b42318",
} satisfies Record<string, `#${string}`>;
```

The `satisfies` operator checks that an expression is compatible with a target type while preserving the expression's more specific inferred type. It is excellent for configuration objects: you get validation of required shape without forcing every property to widen to the annotation's type. Neither feature performs runtime validation or freezing.
