# Primitive and Array Types

TypeScript uses lowercase `string`, `number`, and `boolean` for JavaScript primitive values. Arrays can be written as `T[]` or `Array<T>`. BigInt, symbol, null, and undefined also have corresponding types, with nullability behavior strongly affected by `strictNullChecks`.

```ts
let name: string = "Mina";
let count: number = 3;
let active: boolean = true;

const ids: string[] = ["a", "b"];
const scores: Array<number> = [10, 20];
```

Avoid boxed object types such as `String`, `Number`, and `Boolean` for ordinary values; those describe wrapper objects rather than primitives. Type annotations describe allowed values, not runtime conversion. Declaring a value as `number` does not turn a string into a number—you still need JavaScript conversion logic.
