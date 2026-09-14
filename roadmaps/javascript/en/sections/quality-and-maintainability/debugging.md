# Debugging JavaScript

Modern debuggers can pause execution, inspect lexical scopes, evaluate expressions, step through calls, watch values, inspect network activity, and preserve async stack information. Breakpoints are usually more informative than many temporary logs because you can examine the exact state before it changes.

```js
function calculateTotal(items) {
  debugger;
  return items.reduce((sum, item) => sum + item.price, 0);
}
```

Reproduce a bug with the smallest reliable case, identify the first point where observed state diverges from the expected state, then work backward. Use console output for targeted diagnostics, not application error handling. When code is bundled or transpiled, source maps let debugger locations point back to the modules you authored.
