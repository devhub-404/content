# `keyof` and Indexed Access Types

`keyof T` produces a union of property keys known on a type. An indexed access type `T[K]` retrieves the property type at one or more keys. Together they let generic APIs preserve the relationship between a selected key and the value returned for that key.

```ts
type User = {
  id: string;
  name: string;
  active: boolean;
};

type UserKey = keyof User;       // "id" | "name" | "active"
type UserName = User["name"];    // string

function get<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
```

These operators work entirely in the type system; `keyof` is not runtime reflection. Index signatures affect the resulting key type because JavaScript object keys have string/number coercion behavior. Use constrained keys instead of broad `string` when an API should allow only properties that actually exist.
