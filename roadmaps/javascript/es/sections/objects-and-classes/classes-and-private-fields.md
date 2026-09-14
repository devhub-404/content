# Classes y campos privados

La sintaxis de class define constructors, métodos de prototype, fields, accessors, miembros static y elementos privados. Los métodos de instancia se comparten por el prototype y los fields se inicializan en cada objeto. Los nombres `#privados` tienen privacidad impuesta por el lenguaje.

```js
class Counter {
  #value = 0;

  increment() {
    this.#value += 1;
    return this.#value;
  }

  get value() {
    return this.#value;
  }
}
```

Las clases son strict mode. Getters y setters parecen accesos de propiedad aunque ejecutan código, por lo que conviene mantenerlos predecibles. Usa clases cuando las instancias tengan identidad y comportamiento compartido; para transformaciones de datos o utilidades stateless, objetos y funciones pueden ser más simples.
