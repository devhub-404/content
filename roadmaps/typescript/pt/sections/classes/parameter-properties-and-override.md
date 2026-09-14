# Parameter Properties e `override`

Parameter property combina parâmetro de constructor e declaração de field adicionando access modifier ou `readonly` na lista. Pode reduzir boilerplate em classes pequenas orientadas a dados, embora fields explícitos sejam mais claros quando inicialização é complexa.

```ts
class User {
  constructor(
    public readonly id: string,
    public name: string
  ) {}
}

class Admin extends User {
  override toString() {
    return `Admin(${this.id})`;
  }
}
```

O modifier `override` documenta que método substitui intencionalmente membro da classe base. Com `noImplicitOverride`, TypeScript o exige em overrides, encontrando shadowing acidental após mudanças da API base. Prefira contratos explícitos de herança a subclasses que apenas reutilizam nomes por acaso.
