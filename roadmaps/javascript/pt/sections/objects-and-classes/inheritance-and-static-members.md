# Herança e Membros Static

`extends` cria classe derivada cuja prototype chain das instâncias inclui a classe base. Constructor derivado precisa chamar `super()` antes de usar `this`. `super.method()` invoca comportamento da base a partir de método sobrescrito. Métodos e fields static vivem no constructor da classe, não nas instâncias.

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

Herança é apropriada quando o tipo derivado realmente satisfaz o contrato comportamental da base. Hierarquias profundas tornam estado, inicialização e resolução de métodos difíceis de entender; composição costuma ser mais simples. Membros static funcionam bem para factories, constantes e utilitários que pertencem ao tipo mas não precisam de estado da instância.
