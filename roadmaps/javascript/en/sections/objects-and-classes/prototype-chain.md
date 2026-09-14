# The Prototype Chain

Every ordinary object has an internal prototype reference to another object or null. When a property is not found directly on an object, lookup continues along that prototype chain. Built-in methods such as array methods are usually inherited rather than copied onto every instance.

```js
const animal = {
  speak() {
    return "sound";
  },
};

const dog = Object.create(animal);
dog.name = "Pico";

dog.speak();
```

`Object.create(proto)` creates an object with an explicit prototype and `Object.getPrototypeOf()` inspects it. Constructor functions and class syntax build on the same prototype mechanism. Avoid modifying built-in prototypes in application code: global changes can affect unrelated libraries, feature detection, and future platform behavior.
