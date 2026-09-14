# `Map` e `Set`

`Map` é coleção chaveada cujas chaves podem ser valores de qualquer tipo, inclusive objetos, e cuja iteração preserva ordem de inserção. `Set` armazena valores únicos. Ambos fornecem `has`, `delete`, `clear`, iteração e `size`; Map também fornece `set` e `get`.

```js
const visits = new Map();
visits.set(user, 3);

const tags = new Set(["js", "web", "js"]);
tags.add("css");

console.log(tags.size);
```

Use objetos para dados record-like com nomes de propriedade conhecidos e Map quando as chaves em si são dados dinâmicos. Use Set para membership e unicidade em vez de pesquisar arrays repetidamente. Map e Set usam igualdade SameValueZero: `NaN` pode corresponder a si mesmo, enquanto chaves objeto continuam comparando por identidade.
