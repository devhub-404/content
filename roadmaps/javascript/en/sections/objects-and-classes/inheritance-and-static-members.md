# Inheritance and Static Members

`extends` creates a derived class whose instance prototype chain includes the base class. A derived constructor must call `super()` before using `this`. `super.method()` invokes base behavior from an overriding method. Static methods and fields live on the class constructor rather than on instances.

```js
class User {
  constructor(name) {
    this.name = name;
  }

  describe() {
    return this.name;
  }
}

class Admin extends User {
  static role = "admin";

  describe() {
    return `${super.describe()} (admin)`;
  }
}
```

Inheritance is appropriate when the derived type genuinely satisfies the base type's behavioral contract. Deep hierarchies make state, initialization, and method resolution difficult to understand; composition is often simpler. Static members work well for factories, constants, and utilities that conceptually belong to the type but do not need instance state.
