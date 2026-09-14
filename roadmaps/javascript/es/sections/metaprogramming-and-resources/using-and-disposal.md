# `using` y disposal explícito

Una declaración `using` asocia un binding a un recurso que implementa `[Symbol.dispose]()` y llama ese cleanup automáticamente al salir del scope. Funciona tanto en salida normal como ante errores, return, break o continue, y múltiples recursos se liberan en orden inverso.

```js
class Lock {
  acquire() {
    console.log("locked");
    return this;
  }

  [Symbol.dispose]() {
    console.log("unlocked");
  }
}

{
  using lock = new Lock().acquire();
  // protected work
}
```

Es gestión explícita de locks, handles, subscriptions y recursos con lifecycle externo, no un reemplazo de garbage collection. El recurso debe implementar el protocolo y el binding no puede reasignarse. Si otra referencia escapa del scope, puede apuntar después a un recurso ya disposed.
