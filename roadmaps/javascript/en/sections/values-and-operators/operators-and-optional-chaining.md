# Operators, Short-circuiting, and Optional Chaining

JavaScript has arithmetic, assignment, comparison, logical, bitwise, conditional, property-access, and other operators with defined precedence and associativity. `&&` and `||` short-circuit and return one of their operands rather than forcing a boolean. The conditional operator is an expression for choosing between two values.

```js
const canEdit = signedIn && permissions.includes("edit");
const label = compact ? "Save" : "Save changes";
const city = user.address?.city ?? "Unknown";

settings.theme ??= "system";
```

Optional chaining `?.` stops property access or a call when the base is nullish, and `??` supplies a fallback only for nullish values. Logical assignment operators combine short-circuit logic with assignment. Parentheses are cheap documentation whenever several operator families make the grouping difficult to read from memory.
