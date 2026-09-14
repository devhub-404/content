# Truthiness, valores nullish y coerción

Las condiciones convierten valores a boolean. Son falsy `false`, `0`, `-0`, `0n`, `NaN`, la string vacía, `null` y `undefined`; casi todo lo demás, incluidos arrays y objetos vacíos, es truthy. Los valores nullish son específicamente `null` y `undefined`.

```js
const input = "";
if (!input) {
  console.log("No input");
}

const page = settings.page ?? 1;
const count = Number("42");
```

`??` aplica fallback solo a valores nullish, mientras `||` lo hace para cualquier falsy. Eso importa cuando `0`, `false` o `""` son valores válidos. JavaScript también hace coerción implícita en muchos operadores; usa `Number()`, `String()` o `Boolean()` explícitos cuando la conversión esperada no sea evidente.
