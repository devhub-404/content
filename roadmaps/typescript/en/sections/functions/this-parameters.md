# Typing `this` Parameters

TypeScript can declare a fake first parameter named `this` to describe the receiver expected by an ordinary function. The parameter is erased and does not change runtime calling convention; it only checks that the function is invoked with a compatible receiver.

```ts
interface User {
  name: string;
}

function greet(this: User, message: string) {
  return `${message}, ${this.name}`;
}

const user = { name: "Mina", greet };
user.greet("Hello");
```

This is useful for callback libraries and methods that rely on dynamic JavaScript `this`. Arrow functions cannot declare such a parameter because their `this` is lexical. If an API does not genuinely need receiver semantics, explicit arguments are usually easier to compose and test.
