# Primitive Types

JavaScript has seven primitive types: string, number, bigint, boolean, undefined, symbol, and the special null value. Everything else is an object. Primitive values are immutable, even though a variable that contains one may later be assigned another value.

```js
const name = "Mina";       // string
const count = 42;          // number
const exact = 42n;         // bigint
const active = true;       // boolean
const missing = undefined;
const empty = null;
const key = Symbol("key");
```

`typeof` is useful but has historical quirks: `typeof null` is `"object"`, and arrays also report `"object"`. Use `Array.isArray()` for arrays and explicit checks for null when needed. Symbols are unique primitive identifiers used for property keys and language protocols. BigInt handles arbitrarily large integers but does not mix directly with Number arithmetic.
