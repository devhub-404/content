# JSON

JSON es un formato textual relacionado con object literals de JavaScript pero más limitado. Admite objetos, arrays, strings, numbers, booleans y null. No representa directamente undefined, BigInt, funciones, symbols, Map, Set, Date como tipo propio ni grafos cíclicos.

```js
const text = JSON.stringify({
  id: 42,
  active: true,
});

const value = JSON.parse(text);
```

`JSON.stringify()` serializa valores compatibles y `JSON.parse()` interpreta texto. Parsear JSON crea datos, no código ejecutable, pero esos datos aún necesitan validación de schema y dominio. Un Date suele convertirse en string durante serialización y debe reconstruirse deliberadamente si el dominio lo necesita.
