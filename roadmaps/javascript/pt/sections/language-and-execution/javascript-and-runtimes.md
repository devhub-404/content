# JavaScript e Ambientes de Execução

JavaScript é a linguagem de programação padronizada como ECMAScript. A especificação define sintaxe, valores, objetos, funções, promises, módulos e objetos embutidos. Um runtime cerca essa linguagem com APIs de host. Navegadores fornecem DOM, eventos, Fetch, storage, timers e outras Web APIs; runtimes de servidor oferecem outro ambiente.

```js
const total = 2 + 3;
console.log(total);
```

Essa distinção é fundamental. `Array`, `Map`, `Promise` e `JSON` pertencem ao JavaScript, enquanto `document`, `fetch` e `localStorage` pertencem à plataforma do navegador. A mesma linguagem pode rodar em hosts diferentes, mesmo com globals e recursos de I/O distintos. Aprenda primeiro o modelo da linguagem e depois as APIs do ambiente onde o programa roda.
