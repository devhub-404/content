# Property Descriptors e Accessors

Property descriptor controla comportamento de baixo nível de uma propriedade. Data properties possuem `value` e `writable`; accessor properties possuem getter e setter. Ambas também usam `enumerable` e `configurable`. Assignment normal cria propriedades comuns writable, enumerable e configurable.

```js
const user = {};

Object.defineProperty(user, "id", {
  value: 42,
  writable: false,
  enumerable: true,
  configurable: false,
});
```

Descriptors explicam por que certas propriedades não podem ser reatribuídas, removidas ou vistas em enumeração comum. `Object.keys()`, object spread, `for...in` e APIs de reflection expõem subconjuntos diferentes. Programação em nível de descriptor é importante para bibliotecas e metaprogramação, mas records comuns de aplicação normalmente ficam mais claros com propriedades normais.
