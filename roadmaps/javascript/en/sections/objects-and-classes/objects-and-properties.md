# Objects and Properties

Objects are mutable collections of properties keyed by strings or symbols. Object literals create them concisely, and computed property syntax can use an expression as a key. Dot notation works for identifier-like names; bracket notation is required for dynamic keys and unusual property names.

```js
const field = "email";

const user = {
  id: 42,
  name: "Mina",
  [field]: "mina@example.com",
};

console.log(user.name);
console.log(user["email"]);
```

Reading a missing property normally yields `undefined` after prototype lookup. Assignment can create or update properties, and `delete` removes configurable own properties. Use `Object.hasOwn()` when you need to distinguish an own property from one inherited through the prototype chain. Objects work well as structured records; Maps are often better when keys themselves are dynamic data.
