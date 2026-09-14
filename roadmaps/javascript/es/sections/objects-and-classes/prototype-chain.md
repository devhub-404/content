# La prototype chain

Todo objeto ordinario tiene una referencia interna a otro objeto o a null. Si una propiedad no existe directamente, JavaScript continúa buscándola a lo largo de esa prototype chain. Muchos métodos integrados, como los de Array, son heredados en lugar de copiarse a cada instancia.

```js
const animal = {
  speak() {
    return "sound";
  },
};

const dog = Object.create(animal);
dog.name = "Pico";

dog.speak();
```

`Object.create(proto)` crea un objeto con prototype explícito y `Object.getPrototypeOf()` lo inspecciona. Constructors y classes son capas de más alto nivel sobre el mismo mecanismo. Evita modificar prototypes integrados globalmente porque puede afectar código no relacionado.
