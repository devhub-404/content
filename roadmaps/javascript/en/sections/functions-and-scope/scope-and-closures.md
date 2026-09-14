# Lexical Scope and Closures

JavaScript uses lexical scope: the location where a function is defined determines which outer bindings it can access. A closure is a function together with access to that lexical environment, even after the outer function has finished executing.

```js
function makeCounter() {
  let count = 0;

  return function next() {
    count += 1;
    return count;
  };
}

const next = makeCounter();
next(); // 1
next(); // 2
```

Closures power callbacks, factories, encapsulated module state, memoization, and event handlers. Each call to `makeCounter()` creates a separate `count`. Because captured objects remain reachable while the closure remains reachable, long-lived closures can also retain more memory than intended. Capture the state the callback actually needs.
