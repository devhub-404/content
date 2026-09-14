# Parameters, Defaults, and Rest

JavaScript does not enforce arity at runtime. Missing parameters receive `undefined`, extra arguments are allowed, default parameters replace `undefined` with an expression, and a rest parameter collects remaining arguments into a real array. The rest parameter must be last.

```js
function format(name, prefix = "User", ...tags) {
  return `${prefix}: ${name} [${tags.join(", ")}]`;
}

format("Mina", undefined, "admin", "active");
```

Ordinary functions also expose the array-like `arguments` object, but rest parameters are clearer in modern code and work naturally with array methods. Defaults are evaluated at call time. If a function accumulates many positional parameters, an options object often communicates names, defaults, and future extension better than a long argument list.
