# Statements, Expressions, and Comments

An expression produces a value: a literal, arithmetic operation, function call, property access, or conditional expression. A statement performs a language action such as declaring a binding, branching, looping, returning, or throwing. Expressions frequently appear inside statements, so distinguishing them helps explain where a piece of syntax can be used.

```js
const price = 12;
const total = price * 3;

if (total > 30) {
  console.log("Large order");
}
```

Comments use `//` for one line and `/* ... */` for a block. Good comments explain intent, constraints, or surprising choices rather than paraphrasing obvious code. JavaScript can insert semicolons in defined situations, but automatic semicolon insertion has grammar rules; a consistent formatter and unambiguous line breaks make the issue mostly invisible.
