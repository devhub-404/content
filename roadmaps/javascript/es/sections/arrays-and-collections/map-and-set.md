# `Map` y `Set`

`Map` almacena pares clave/valor donde las claves pueden ser de cualquier tipo, incluso objetos, y preserva orden de inserción al iterar. `Set` almacena valores únicos. Ambos ofrecen operaciones de membership, eliminación, limpieza e iteración.

```js
const visits = new Map();
visits.set(user, 3);

const tags = new Set(["js", "web", "js"]);
tags.add("css");

console.log(tags.size);
```

Usa objetos para records con propiedades conocidas y Map cuando las claves sean datos dinámicos. Usa Set para unicidad y membership. Map y Set usan SameValueZero: `NaN` puede coincidir consigo mismo y las claves objeto siguen comparándose por identidad.
