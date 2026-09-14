# Array Destructuring and Spread

Array destructuring reads values from an iterable by position and can skip values, provide defaults, nest patterns, or collect the remainder. Spread expands an iterable into an array literal, argument list, or other supported syntax. Both features work with iterables, not only actual arrays.

```js
const [first, second, ...rest] = items;
const copy = [...items];
const combined = [...left, ...right];

function point([x, y]) {
  return { x, y };
}
```

`[...array]` makes a shallow copy, so nested object identity is shared. Spreading a very large iterable into function arguments can hit runtime argument limits. Destructuring function parameters is concise for small fixed tuple-like inputs, but complex nested patterns can obscure the shape that callers are expected to supply.
