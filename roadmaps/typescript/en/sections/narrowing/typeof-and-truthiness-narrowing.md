# `typeof` and Truthiness Narrowing

TypeScript follows control flow to narrow a broad type into a more specific one. `typeof` checks narrow primitive categories, while explicit equality checks can remove null or match literal values. Truthiness checks also narrow, but they can accidentally exclude valid falsy values such as `0` or the empty string.

```ts
function format(value: string | number | null) {
  if (value === null) return "none";

  if (typeof value === "number") {
    return value.toFixed(2);
  }

  return value.toUpperCase();
}
```

Write runtime checks that reflect the domain rule first; the type narrowing should follow naturally. If `0` is a valid value, check `value !== undefined` rather than `if (value)`. Good TypeScript code rarely needs to tell the checker facts that ordinary JavaScript control flow can already prove.
