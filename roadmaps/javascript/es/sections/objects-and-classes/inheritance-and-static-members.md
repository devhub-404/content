# Herencia y miembros static

`extends` crea una clase derivada cuya prototype chain incluye la clase base. Un constructor derivado debe llamar `super()` antes de usar `this`, y `super.metodo()` permite invocar comportamiento de la base. Los miembros static viven en el constructor, no en las instancias.

```js
class User {
  constructor(name) {
    this.name = name;
  }

  describe() {
    return this.name;
  }
}

class Admin extends User {
  static role = "admin";

  describe() {
    return `${super.describe()} (admin)`;
  }
}
```

Herencia tiene sentido cuando el subtipo satisface realmente el contrato comportamental del tipo base. Jerarquías profundas complican estado e inicialización; composición suele producir dependencias más pequeñas. Miembros static son útiles para factories, constantes y utilidades ligadas al tipo.
