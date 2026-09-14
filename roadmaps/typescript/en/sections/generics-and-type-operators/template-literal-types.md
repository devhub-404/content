# Template Literal Types

Template literal types build string literal types by interpolating other literal types. When a substituted position is a union, TypeScript forms the corresponding combinations. This is useful for event names, route patterns, property-derived APIs, and other string conventions that have real structure.

```ts
type EventName<T extends string> = `${T}Changed`;

type Field = "name" | "email";
type FieldEvent = EventName<Field>;
// "nameChanged" | "emailChanged"
```

These types describe compile-time string relationships; they do not parse or validate arbitrary runtime strings by themselves. Large cross-products of unions can become expensive and hard to read. Prefer generated data or simpler string types when the vocabulary is huge rather than forcing the checker to enumerate thousands of combinations.
