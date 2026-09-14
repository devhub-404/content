# Fields de Classe e Tipos de Constructor

TypeScript verifica instance fields, constructors, métodos, accessors e membros static preservando semântica de runtime das classes JavaScript. Fields precisam de definite initialization, initializer ou configuração que explique por que existirão.

```ts
class User {
  id: string;
  name: string;

  constructor(id: string, name: string) {
    this.id = id;
    this.name = name;
  }
}
```

Nome de classe normalmente introduz tipo de instância e valor constructor em runtime, conforme a posição. `typeof User` descreve o lado constructor, enquanto `User` em posição de tipo descreve instâncias. Mantenha esse modelo de dois lados em mente ao escrever factories ou constraints de constructor.
