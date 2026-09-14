# Property descriptors y accessors

Cada propiedad posee un descriptor. Una data property tiene `value` y `writable`; una accessor property usa getter/setter. Ambas pueden ser `enumerable` y `configurable`. Assignment normal crea propiedades con un conjunto común de flags.

```js
const user = {};

Object.defineProperty(user, "id", {
  value: 42,
  writable: false,
  enumerable: true,
  configurable: false,
});
```

Los descriptors explican por qué ciertas propiedades no se pueden reasignar, borrar o enumerar. `Object.keys()`, spread, `for...in` y APIs de reflection muestran subconjuntos distintos. Trabajar a este nivel es útil para bibliotecas y metaprogramación, pero los datos de negocio normales suelen ser más claros con propiedades ordinarias.
