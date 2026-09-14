# Type Erasure and Runtime Values

Type aliases, interfaces, generic arguments, and most other TypeScript type syntax do not exist at runtime. They guide the checker and editor, then disappear from emitted JavaScript. You cannot generally ask JavaScript whether a runtime object “implements an interface” because that interface has been erased.

```ts
type UserId = string;

interface User {
  id: UserId;
  name: string;
}

const user: User = { id: "u1", name: "Mina" };
console.log(user.name);
```

Runtime validation therefore needs runtime data: `typeof`, `instanceof`, property checks, schemas, parsers, or validation libraries. Classes and enums can create runtime values, while interfaces and type aliases do not. Keep the distinction between the type world and value world clear when designing APIs or debugging generated JavaScript.
