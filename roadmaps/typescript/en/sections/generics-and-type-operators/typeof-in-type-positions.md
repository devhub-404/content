# `typeof` in Type Positions

TypeScript's type-position `typeof` obtains the static type of a value or property that already exists in code. It is different from JavaScript's runtime `typeof` operator even though they share spelling.

```ts
const defaults = {
  retries: 3,
  mode: "safe" as const,
};

type Defaults = typeof defaults;

function configure(options: Partial<Defaults>) {
  // ...
}
```

This is useful when a value is the source of truth and you want types to follow it instead of duplicating an object shape. Type-position `typeof` is intentionally limited to identifiers and property accesses rather than arbitrary runtime expressions, which keeps type extraction predictable.
