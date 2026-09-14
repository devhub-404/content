# Loops and Iteration Statements

`for` exposes initialization, condition, and update steps. `while` repeats while a condition remains truthy, and `do...while` executes its body at least once. `for...of` iterates values from an iterable such as an array, string, Map, Set, or generator.

```js
for (let i = 0; i < 3; i++) {
  console.log(i);
}

for (const item of items) {
  console.log(item);
}

while (queue.length > 0) {
  process(queue.shift());
}
```

`for...in` iterates enumerable property keys and is mainly for property enumeration, not array values. `break` exits a loop and `continue` starts the next iteration. Prefer collection methods when the operation is naturally `map`, `filter`, or a search; prefer a loop when the control flow itself—early exits, retries, multiple state changes—is central.
