# Mapped Types

A mapped type iterates over a union of property keys to build a new object type. The common source is `keyof T`. Mapping modifiers can add or remove `readonly` and optional markers, which is how many standard utility types are expressed.

```ts
type Flags<T> = {
  [K in keyof T]: boolean;
};

type Mutable<T> = {
  -readonly [K in keyof T]-?: T[K];
};
```

Mapped types are ideal for systematic transformations such as “same keys, different value type” or “all properties optional.” Key remapping with `as` can rename or filter keys. Keep transformation names meaningful; a dense stack of mapped and conditional helpers can make editor error messages much harder to interpret.
