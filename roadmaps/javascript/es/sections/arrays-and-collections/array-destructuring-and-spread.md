# Array destructuring y spread

Array destructuring obtiene valores de un iterable por posición y puede saltar elementos, usar defaults, anidar patrones o recoger el resto. Spread expande un iterable dentro de un array literal, lista de argumentos u otros contextos compatibles.

```js
const [first, second, ...rest] = items;
const copy = [...items];
const combined = [...left, ...right];

function point([x, y]) {
  return { x, y };
}
```

`[...array]` hace una copia superficial. Expandir un iterable enorme como argumentos puede superar límites del runtime. Destructuring en parámetros funciona bien para pequeños tuples, pero patrones muy anidados pueden ocultar la forma que el caller debe proporcionar.
