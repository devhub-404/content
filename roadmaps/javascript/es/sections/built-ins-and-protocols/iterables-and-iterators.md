# Iterables e iterators

Un iterable implementa `[Symbol.iterator]()` y devuelve un iterator. El iterator tiene `next()` y produce `{ value, done }`. `for...of`, spread de arrays, destructuring, `Array.from()` y constructors de Map/Set consumen este protocolo.

```js
const range = {
  from: 1,
  to: 3,
  *[Symbol.iterator]() {
    for (let value = this.from; value <= this.to; value++) {
      yield value;
    }
  },
};

console.log([...range]);
```

El iterator es un cursor con estado y el iterable es el objeto capaz de proporcionar uno. Algunas estructuras crean un iterator nuevo en cada recorrido; otras son su propio iterator y se consumen una sola vez. Esa diferencia explica por qué un generator result normalmente no puede repetirse sin crear otro.
