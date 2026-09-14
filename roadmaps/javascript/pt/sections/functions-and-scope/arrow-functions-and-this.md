# Arrow Functions e `this` Léxico

Arrow functions são function expressions compactas. Uma expressão única pode ser retornada implicitamente; corpo em bloco precisa de `return`. Mais importante, arrows não criam bindings próprios de `this`, `arguments`, `super` ou `new.target`. Elas capturam valores relevantes do contexto léxico ao redor.

```js
const double = value => value * 2;

const counter = {
  value: 0,
  start() {
    setTimeout(() => {
      this.value += 1;
    }, 100);
  },
};
```

Isso torna arrows excelentes para callbacks que devem manter o receiver do método externo, mas frequentemente erradas como método de objeto que precisa de `this` dinâmico. Arrows também não podem ser constructors com `new`. Escolha a sintaxe pela semântica em vez de tratar arrows como substitutas universalmente mais novas.
