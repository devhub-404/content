# `let`, `const`, and `var`

Use `const` when the binding itself will not be reassigned and `let` when reassignment is part of the algorithm. Both are block-scoped and remain in the temporal dead zone until initialization. `const` does not make an object immutable; it only prevents assigning a different value to that binding.

```js
const taxRate = 0.2;
let total = 100;
total += total * taxRate;

if (total > 100) {
  const message = "Large total";
  console.log(message);
}
```

`var` is function-scoped, is initialized to `undefined` during hoisting, and can be redeclared in the same scope. Existing JavaScript still contains it, so understand the behavior, but new code is usually clearer with `const` and `let`. Declare values near the point where their meaningful lifetime begins instead of creating large mutable scopes.
