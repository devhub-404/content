# JSON

JSON is a text data format related to JavaScript object literal syntax but more restricted. It supports objects, arrays, strings, numbers, booleans, and null. It does not directly represent undefined, BigInt, functions, symbols, Map, Set, Date as a distinct type, or cyclic object graphs.

```js
const text = JSON.stringify({
  id: 42,
  active: true,
});

const value = JSON.parse(text);
```

`JSON.stringify()` serializes supported data and can use a replacer; `JSON.parse()` parses text and can use a reviver. Parsing JSON creates data, not executable JavaScript, but external values still need schema and domain validation. Dates commonly become strings during serialization and must be interpreted intentionally when read again.
