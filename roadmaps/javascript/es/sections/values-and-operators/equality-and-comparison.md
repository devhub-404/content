# Igualdad y comparación

`===` y `!==` comparan sin la coerción amplia de `==` y `!=`, por lo que la igualdad estricta es el punto de partida normal. Los objetos se comparan por identidad: dos object literals distintos no son iguales solo porque contengan los mismos datos.

```js
0 === false;          // false
0 == false;           // true
Object.is(NaN, NaN);  // true

const sameUser = a.id === b.id;
```

`Object.is()` ofrece otra relación de igualdad que considera `NaN` igual a sí mismo y distingue `0` de `-0`. Map y Set usan una relación definida propia. Para objetos de dominio, decide qué significa igualdad—identidad, un ID o datos equivalentes—y exprésalo explícitamente.
