# Functions and Return Values

Functions are callable objects. A function declaration creates a named binding that is initialized during scope setup; a function expression creates a function as an expression and can be stored wherever a value can be stored. Calling a function creates its own local execution context.

```js
function add(a, b) {
  return a + b;
}

const multiply = function (a, b) {
  return a * b;
};
```

`return` ends the current invocation and supplies a result. Reaching the end without a returned expression produces `undefined`. Named functions improve stack traces and recursion. Prefer functions with clear inputs, outputs, and side effects, but do not split a straightforward operation into helpers whose names add no information.
