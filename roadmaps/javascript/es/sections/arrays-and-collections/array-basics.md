# Fundamentos de arrays

Los arrays son objetos especializados para datos ordenados e indexados desde cero. Tienen comportamiento especial de `length` y pueden ser sparse, aunque los arrays densos son más fáciles de razonar. `Array.isArray()` es el check fiable para saber si un valor es un array.

```js
const items = ["a", "b", "c"];
items.push("d");

console.log(items[0]);
console.log(items.at(-1));
console.log(items.length);
```

Métodos como `push`, `pop`, `splice`, `sort` y `reverse` mutan el array; otros devuelven nuevos valores o arrays. Conoce el comportamiento antes de trabajar con estado compartido. `.at()` ofrece indexación positiva o negativa sin cambiar el modelo base.
