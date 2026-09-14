# Tipos primitivos

JavaScript tiene siete tipos primitivos: string, number, bigint, boolean, undefined, symbol y null como valor especial. Todo lo demás es un objeto. Los valores primitivos son inmutables aunque una variable que los contiene pueda recibir otro valor más tarde.

```js
const name = "Mina";       // string
const count = 42;          // number
const exact = 42n;         // bigint
const active = true;       // boolean
const missing = undefined;
const empty = null;
const key = Symbol("key");
```

`typeof` es útil, pero tiene peculiaridades históricas: `typeof null` devuelve `"object"` y los arrays también son objetos. Usa `Array.isArray()` para arrays y checks explícitos para null. Symbols sirven como identificadores únicos y BigInt representa enteros arbitrariamente grandes sin mezclarse directamente con Number.
