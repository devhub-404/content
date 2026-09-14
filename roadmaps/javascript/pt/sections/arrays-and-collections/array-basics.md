# Fundamentos de Arrays

Arrays são objetos especializados para dados ordenados e indexados. Usam índices começando em zero e comportamento especial de `length`. JavaScript pode representar sparse arrays com índices ausentes, mas arrays densos são mais fáceis de raciocinar e normalmente melhores para dados da aplicação. Use `Array.isArray()` para testar array.

```js
const items = ["a", "b", "c"];
items.push("d");

console.log(items[0]);
console.log(items.at(-1));
console.log(items.length);
```

Alguns métodos mutam o array, incluindo `push`, `pop`, `shift`, `unshift`, `splice`, `sort` e `reverse`; muitos outros retornam outro valor ou array. Conheça o comportamento de mutação antes de operar em estado compartilhado. `.at()` fornece indexação positiva ou negativa conveniente sem mudar o modelo zero-based.
