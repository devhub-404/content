# Loops y statements de iteración

`for` expone inicialización, condición y actualización. `while` repite mientras una condición sea truthy y `do...while` ejecuta el cuerpo al menos una vez. `for...of` recorre valores de un iterable como array, string, Map, Set o generator.

```js
for (let i = 0; i < 3; i++) {
  console.log(i);
}

for (const item of items) {
  console.log(item);
}

while (queue.length > 0) {
  process(queue.shift());
}
```

`for...in` recorre claves de propiedades enumerables y no es el equivalente de `for...of` para arrays. `break` sale del loop y `continue` pasa a la siguiente iteración. Usa métodos de colección cuando expresan claramente una transformación y loops cuando el control de flujo sea la parte importante.
