# Array Basics

Arrays are specialized objects for ordered indexed data. They use zero-based indexes and array-specific length behavior. JavaScript can represent sparse arrays with missing indexes, but dense arrays are easier to reason about and usually a better choice for application data. Use `Array.isArray()` to test for an array.

```js
const items = ["a", "b", "c"];
items.push("d");

console.log(items[0]);
console.log(items.at(-1));
console.log(items.length);
```

Some methods mutate the array, including `push`, `pop`, `shift`, `unshift`, `splice`, `sort`, and `reverse`; many others return another value or array. Know the mutation behavior before operating on shared state. `.at()` provides convenient positive or negative indexing without changing the underlying zero-based model.
