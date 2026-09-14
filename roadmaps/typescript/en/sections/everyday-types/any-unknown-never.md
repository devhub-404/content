# `any`, `unknown`, and `never`

`any` opts out of much of TypeScript's checking and lets unsafe operations flow through the program. Use it at deliberate escape hatches, not as the default answer to a difficult type. `unknown` can hold any value too, but you must narrow it before using operations that depend on a more specific type.

```ts
function parse(value: string): unknown {
  return JSON.parse(value);
}

function fail(message: string): never {
  throw new Error(message);
}
```

`never` represents values that cannot occur, such as a function that always throws or an impossible branch after exhaustive narrowing. It is especially useful for checking that a discriminated union has been fully handled. Think of `unknown` as “I do not know yet” and `never` as “there is no value here.”
