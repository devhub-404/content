# Scope léxico y closures

JavaScript usa scope léxico: el lugar donde una función se define determina qué bindings exteriores puede ver. Una closure es la función junto con acceso a ese entorno léxico, incluso después de que la función exterior haya terminado.

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

Closures permiten callbacks, factories, estado privado de módulos, memoización y handlers. Cada llamada puede crear un entorno independiente. También mantienen reachable cualquier objeto capturado, por lo que una closure long-lived puede retener más memoria de la prevista si captura demasiado estado.
