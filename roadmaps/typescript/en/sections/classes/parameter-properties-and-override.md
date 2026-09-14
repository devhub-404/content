# Parameter Properties and `override`

A parameter property combines a constructor parameter and class field declaration by adding an access modifier or `readonly` in the parameter list. It can reduce boilerplate for small data-oriented classes, though explicit fields may be clearer when initialization is more involved.

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

The `override` modifier documents that a method intentionally replaces a base-class member. With `noImplicitOverride`, TypeScript requires it when overriding, catching accidental shadowing after base APIs change. Prefer explicit inheritance contracts over subclasses that happen to reuse names without acknowledging the relationship.
