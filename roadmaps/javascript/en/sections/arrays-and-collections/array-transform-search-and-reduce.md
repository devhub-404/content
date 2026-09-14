# Transforming, Searching, and Reducing Arrays

Array iteration methods describe common collection operations directly. `map` transforms every element, `filter` keeps matching values, `find` returns the first matching value, `findIndex` returns its index, `some` asks whether any match, and `every` asks whether all match.

```js
const activeNames = users
  .filter(user => user.active)
  .map(user => user.name);

const admin = users.find(user => user.role === "admin");
const allValid = users.every(user => user.name.length > 0);
const total = prices.reduce((sum, price) => sum + price, 0);
```

`reduce` combines a sequence into an accumulator and is powerful enough to express many operations, but a dedicated method or named loop is often clearer than an overly clever reducer. Callbacks receive the current value, index, and array. Prefer these methods when they make the data flow obvious; use loops when early exits or complex control flow matter more.
