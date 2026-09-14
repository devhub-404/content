# Prototype Chain

Todo objeto comum possui referência interna de prototype para outro objeto ou null. Quando uma propriedade não é encontrada diretamente, a busca continua pela prototype chain. Métodos embutidos como os de arrays normalmente são herdados em vez de copiados para cada instância.

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

`Object.create(proto)` cria objeto com prototype explícito e `Object.getPrototypeOf()` o inspeciona. Constructor functions e sintaxe de class usam o mesmo mecanismo de prototype por baixo. Evite modificar prototypes embutidos em aplicações: mudanças globais podem afetar bibliotecas, feature detection e comportamento futuro da plataforma.
