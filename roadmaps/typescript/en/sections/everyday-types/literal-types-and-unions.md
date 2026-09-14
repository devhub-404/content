# Literal Types and Unions

A literal type represents one exact value, such as `"dark"` or `200`. Union types combine alternatives with `|`, letting an API describe values that can legitimately have several shapes. Literals plus unions are often better than a broad `string` when the allowed vocabulary is known.

```ts
type Theme = "light" | "dark" | "system";
type Id = string | number;

function setTheme(theme: Theme) {
  // ...
}
```

Operations on a union must be safe for every member until control flow narrows the type. Union design is central to TypeScript: instead of making every property optional on one giant object, model genuinely different states as separate members. This makes invalid combinations harder to represent.
