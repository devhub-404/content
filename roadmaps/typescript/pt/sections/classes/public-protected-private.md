# `public`, `protected` e `private`

Access modifiers do TypeScript controlam qual código o checker permite acessar membros da classe. `public` é padrão, `protected` permite classe e subclasses, e `private` do TypeScript restringe acesso no type checking. Esses modifiers são principalmente construções de compile time.

```ts
class Account {
  public owner: string;
  protected balance = 0;
  private auditCode = "internal";

  constructor(owner: string) {
    this.owner = owner;
  }
}
```

Fields JavaScript `#private` fornecem privacidade com enforcement de runtime e possuem semântica diferente. Escolha `#private` quando encapsulamento em runtime importa; escolha `private` do TypeScript quando fronteira de API em compile time basta e requisitos de emissão importam. Evite expor internals mutáveis como public apenas porque TypeScript consegue tipá-los.
