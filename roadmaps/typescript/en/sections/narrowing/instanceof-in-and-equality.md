# `instanceof`, `in`, and Equality Narrowing

`instanceof` narrows using a runtime constructor relationship. The `in` operator can narrow unions based on whether a property exists. Equality between related variables or against literals can also make the checker infer a common compatible type.

```ts
function read(value: Date | { text: string }) {
  if (value instanceof Date) {
    return value.toISOString();
  }

  if ("text" in value) {
    return value.text;
  }

  return "";
}
```

These checks are only as meaningful as the runtime model. Interfaces disappear at runtime, so `instanceof SomeInterface` is impossible. Cross-realm objects can also make constructor identity surprising. Prefer discriminants or explicit validation for plain data and reserve `instanceof` for actual class/constructor relationships.
