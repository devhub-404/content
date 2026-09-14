# `public`, `protected`, and `private`

TypeScript access modifiers control which code the checker allows to access class members. `public` is the default, `protected` allows the class and subclasses, and TypeScript `private` restricts access in type checking. These modifiers are primarily compile-time constructs.

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

JavaScript `#private` fields provide runtime-enforced privacy and have different semantics. Choose `#private` when runtime encapsulation matters; choose TypeScript `private` when compile-time API boundaries are sufficient and emitted compatibility requirements matter. Avoid exposing mutable internals as public fields simply because TypeScript can type them.
