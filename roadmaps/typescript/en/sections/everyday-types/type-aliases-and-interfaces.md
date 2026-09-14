# Type Aliases and Interfaces

Both type aliases and interfaces can describe object shapes. Interfaces are designed around named object contracts and can participate in declaration merging and `extends`. Type aliases can name any type expression, including unions, tuples, primitives, mapped types, and conditional types.

```ts
type Point = {
  x: number;
  y: number;
};

interface User {
  id: string;
  name: string;
}
```

For ordinary object modeling, either can be correct; consistency and the required language features matter more than slogans such as “always use interface.” Use interface when open/mergeable object contracts are intentional, and type aliases when composing arbitrary type expressions. Neither creates a runtime constructor or validator.
