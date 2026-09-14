# Arrow functions y `this` léxico

Las arrow functions son function expressions compactas. Un cuerpo de una sola expresión puede retornarla implícitamente, mientras un bloque necesita `return`. La diferencia semántica clave es que una arrow no crea sus propios bindings de `this`, `arguments`, `super` o `new.target`.

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

El `this` léxico es muy útil en callbacks que deben conservar el receiver exterior, pero suele ser incorrecto para métodos que necesitan un receiver dinámico. Las arrows tampoco pueden usarse con `new`. Elige la sintaxis por su semántica, no solo porque sea más corta.
