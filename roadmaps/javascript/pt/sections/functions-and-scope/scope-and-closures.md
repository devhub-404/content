# Escopo Léxico e Closures

JavaScript usa escopo léxico: o local onde uma função é definida determina quais bindings externos ela pode acessar. Closure é a função junto com acesso àquele ambiente léxico, mesmo depois que a função externa terminou de executar.

```js
function makeCounter() {
  let count = 0;

  return function next() {
    count += 1;
    return count;
  };
}

const next = makeCounter();
next(); // 1
next(); // 2
```

Closures sustentam callbacks, factories, estado encapsulado de módulo, memoization e event handlers. Cada chamada de `makeCounter()` cria um `count` separado. Como objetos capturados continuam reachable enquanto a closure estiver reachable, closures long-lived também podem reter memória além do necessário. Capture apenas o estado realmente usado pelo callback.
