# Transformando, Buscando e Reduzindo Arrays

Métodos de iteração de array descrevem diretamente operações comuns de coleção. `map` transforma cada elemento, `filter` mantém valores correspondentes, `find` retorna o primeiro valor correspondente, `findIndex` seu índice, `some` pergunta se algum corresponde e `every` se todos correspondem.

```js
const activeNames = users
  .filter(user => user.active)
  .map(user => user.name);

const admin = users.find(user => user.role === "admin");
const allValid = users.every(user => user.name.length > 0);
const total = prices.reduce((sum, price) => sum + price, 0);
```

`reduce` combina sequência em acumulador e é poderoso o bastante para expressar muitas operações, mas método dedicado ou loop nomeado costuma ser mais claro que reducer excessivamente engenhoso. Callbacks recebem valor atual, índice e array. Prefira esses métodos quando deixam o fluxo de dados óbvio; use loops quando saídas antecipadas ou controle complexo importarem mais.
