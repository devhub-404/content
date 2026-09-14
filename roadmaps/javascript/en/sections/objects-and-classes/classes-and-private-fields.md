# Classes and Private Fields

Class syntax defines constructors, prototype methods, fields, accessors, static members, and private elements. Instance methods are shared through the prototype; instance fields are initialized for each instance. Names beginning with `#` are language-enforced private names and cannot be accessed from outside the declaring class body.

```js
class Counter {
  #value = 0;

  increment() {
    this.#value += 1;
    return this.#value;
  }

  get value() {
    return this.#value;
  }
}
```

Classes are strict-mode code. Getters and setters use property syntax while executing code, so keep them predictable and avoid hidden expensive work. Classes are useful when objects have identity and shared behavior; plain objects and functions are often simpler for data transformation or stateless utilities.
