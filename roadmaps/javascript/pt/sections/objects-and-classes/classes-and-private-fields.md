# Classes e Private Fields

Sintaxe de class define constructors, métodos de prototype, fields, accessors, membros static e elementos privados. Métodos de instância são compartilhados pelo prototype; instance fields são inicializados para cada instância. Nomes iniciados por `#` são privados com enforcement da linguagem e não podem ser acessados de fora da classe declaradora.

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

Classes são código strict. Getters e setters usam sintaxe de propriedade enquanto executam código, então mantenha-os previsíveis e evite trabalho caro escondido. Classes são úteis quando objetos possuem identidade e comportamento compartilhado; objetos simples e funções costumam ser mais simples para transformação de dados ou utilitários sem estado.
