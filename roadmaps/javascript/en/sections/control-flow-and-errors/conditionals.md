# Conditionals

`if`, `else if`, and `else` branch according to truthiness. The conditional operator `condition ? a : b` is useful when an expression should choose one of two values; deeply nested ternaries usually become harder to read than ordinary branching.

```js
if (score >= 90) {
  grade = "A";
} else if (score >= 80) {
  grade = "B";
} else {
  grade = "C";
}

const status = active ? "online" : "offline";
```

`switch` compares one expression against discrete cases using strict equality and is useful when several known values choose different paths. Cases fall through until `break`, `return`, or another abrupt completion stops execution, so intentional fallthrough should be obvious. Choose the structure that makes the rules easiest to inspect.
