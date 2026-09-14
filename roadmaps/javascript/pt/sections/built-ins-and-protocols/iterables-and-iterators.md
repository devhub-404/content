# Iterables e Iterators

Um iterable fornece `[Symbol.iterator]()` retornando iterator. Um iterator expõe `next()`, que retorna `{ value, done }`. `for...of`, array spread, destructuring, `Array.from()` e constructors Set/Map consomem esse protocolo, permitindo que estruturas customizadas participem da sintaxe normal.

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

Iterator é cursor stateful, enquanto iterable é o objeto capaz de fornecer um. Alguns objetos retornam iterator novo a cada vez; outros são seu próprio iterator e podem ser consumidos apenas uma vez. Essa distinção explica por que certas sequências podem ser percorridas repetidamente enquanto resultados de generator normalmente não são replayable sem criar novo generator.
