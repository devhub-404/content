# Class Fields and Constructor Types

TypeScript checks class instance fields, constructors, methods, accessors, and static members while preserving JavaScript class runtime semantics. Fields need either definite initialization, an initializer, or another configuration that explains why they will exist.

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

A class name usually introduces both an instance type and a runtime constructor value, depending on where it is used. `typeof User` describes the constructor side, while `User` in a type position describes instances. Keep that two-sided model in mind when writing factories or generic constructor constraints.
