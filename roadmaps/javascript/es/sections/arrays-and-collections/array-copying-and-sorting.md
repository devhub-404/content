# Copiar y ordenar arrays

`sort()`, `reverse()` y `splice()` tradicionales mutan el array. `toSorted()`, `toReversed()`, `toSpliced()` y `with()` devuelven una copia modificada y preservan el original, lo que ayuda en arquitecturas que tratan el estado como valores antes/después.

```js
const sorted = users.toSorted((a, b) =>
  a.name.localeCompare(b.name)
);

const reversed = items.toReversed();
const updated = items.with(1, "new value");
const removed = items.toSpliced(2, 1);
```

El sort por defecto compara strings, así que números suelen necesitar `(a, b) => a - b`. Para texto dependiente de locale usa `localeCompare()` o `Intl.Collator`. Las copias siguen siendo superficiales: los objetos internos son las mismas referencias.
