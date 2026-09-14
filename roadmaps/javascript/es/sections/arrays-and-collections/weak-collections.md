# Weak collections

`WeakMap` y `WeakSet` mantienen ciertas claves de forma débil, de modo que la colección no impide por sí sola que el garbage collector elimine una clave inaccesible. `WeakMap` es útil para asociar metadata a la identidad de objetos.

```js
const metadata = new WeakMap();

function attachMetadata(element, data) {
  metadata.set(element, data);
}

function getMetadata(element) {
  return metadata.get(element);
}
```

No pueden enumerarse ni tienen `size` porque la recolección es no determinista. Por eso no sirven para colecciones que necesitas listar o contar. Ayudan con asociaciones ligadas al lifecycle, pero no sustituyen cleanup explícito de handles, listeners o subscriptions.
