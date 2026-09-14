# Parameter properties y `override`

Un parameter property combina un parámetro de constructor con un field al añadir `public`, `protected`, `private` o `readonly` en la lista de parámetros. Reduce boilerplate en clases pequeñas orientadas a datos.

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

`override` documenta que un método sustituye intencionalmente uno de la base. Con `noImplicitOverride`, TypeScript obliga a declararlo y detecta shadowing accidental cuando cambia la clase padre. Las relaciones de herencia importantes deberían ser explícitas.
