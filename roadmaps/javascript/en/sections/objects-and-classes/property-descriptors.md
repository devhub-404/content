# Property Descriptors and Accessors

A property descriptor controls an object's low-level property behavior. Data properties have `value` and `writable`; accessor properties have getter and setter functions. Both forms also use `enumerable` and `configurable`. Normal assignment creates common writable, enumerable, configurable properties.

```js
const user = {};

Object.defineProperty(user, "id", {
  value: 42,
  writable: false,
  enumerable: true,
  configurable: false,
});
```

Descriptors explain why some properties cannot be reassigned, deleted, or observed by ordinary enumeration. `Object.keys()`, object spread, `for...in`, and reflection APIs intentionally expose different subsets of properties. Descriptor-level programming is important for libraries and metaprogramming, but ordinary application records are usually clearer with normal properties.
