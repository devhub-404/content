# Callbacks and Higher-order Functions

Functions are first-class values: they can be stored, passed, returned, and placed in data structures. A callback is a function passed for another operation to invoke. A higher-order function receives functions, returns functions, or both. Array methods, promises, event listeners, middleware, and composition all use this model.

```js
function repeat(times, action) {
  for (let i = 0; i < times; i++) {
    action(i);
  }
}

repeat(3, index => console.log(index));
```

A callback may run synchronously, asynchronously, once, or many times depending on the API, so the callback contract matters. Do not assume passing a function automatically makes something asynchronous. Keep captured state explicit; when callbacks become deeply nested, extract named steps or use a better abstraction such as promise composition.
