# Fields de clase y tipos de constructor

TypeScript comprueba fields, constructors, métodos, accessors y miembros static conservando la semántica de classes de JavaScript. Los fields deben quedar inicializados de una forma que el checker pueda demostrar o que la configuración permita.

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

El nombre de una clase puede representar dos cosas: `User` como tipo de instancias y `typeof User` como tipo del constructor. Esa diferencia es importante al escribir factories o constraints genéricos sobre classes.
