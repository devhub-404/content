# Object Spread and Destructuring

Object spread copies enumerable own properties into a new object in order, so later properties overwrite earlier ones with the same key. It is a shallow copy: nested objects and arrays remain shared references. Shorthand property syntax lets `{ name }` mean `{ name: name }`.

```js
const user = { name: "Mina", role: "admin" };
const updated = { ...user, role: "editor" };

const {
  name: displayName,
  role = "guest",
} = updated;
```

Destructuring extracts properties into bindings and supports renaming, defaults, nested patterns, and rest properties. A default applies only when the extracted value is `undefined`, not when it is `null`, `false`, or another falsy value. Spread is convenient for data records, but it does not preserve an object's full descriptor or prototype behavior.
