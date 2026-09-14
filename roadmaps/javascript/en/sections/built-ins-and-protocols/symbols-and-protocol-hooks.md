# Symbols and Protocol Hooks

A Symbol is a unique primitive commonly used as a property key that will not collide with ordinary string keys. `Symbol()` always creates a new symbol, while `Symbol.for()` uses a global symbol registry. Symbol-keyed properties are omitted by several ordinary string-key enumeration operations.

```js
const internalId = Symbol("internalId");

const record = {
  [internalId]: 42,
  [Symbol.toStringTag]: "Record",
};
```

Well-known symbols define language protocols and customization hooks for iteration, async iteration, primitive conversion, matching, species behavior, disposal, object tags, and more. Implement these hooks only when a type truly participates in the corresponding protocol. Symbols provide identity and protocol keys; they are not a security boundary for private data.
