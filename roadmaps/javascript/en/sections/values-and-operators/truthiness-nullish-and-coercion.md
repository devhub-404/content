# Truthiness, Nullish Values, and Coercion

Conditions convert values to boolean. The falsy values are `false`, `0`, `-0`, `0n`, `NaN`, the empty string, `null`, and `undefined`; almost everything else, including empty arrays and objects, is truthy. Nullish values are specifically only `null` and `undefined`.

```js
const input = "";
if (!input) {
  console.log("No input");
}

const page = settings.page ?? 1;
const count = Number("42");
```

`??` falls back only for nullish values, unlike `||`, which falls back for every falsy value. This matters when `0`, `false`, or `""` are meaningful. JavaScript also performs implicit coercion in many operators, especially `+`. Prefer explicit `Number()`, `String()`, or `Boolean()` at boundaries when the intended conversion would otherwise be unclear.
