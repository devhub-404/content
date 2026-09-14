# Interface Extension and Object Composition

Interfaces can extend one or more object types, producing a named contract that includes inherited members. This is type-level composition and does not create runtime prototype inheritance. A plain object can satisfy `Admin` without being an instance of any class.

```ts
interface Entity {
  id: string;
}

interface User extends Entity {
  name: string;
}

interface Admin extends User {
  permissions: string[];
}
```

Use extension when the relationship communicates a stable subtype contract. For ad-hoc type transformations or unions, type aliases and intersections may be more expressive. Avoid building deep type hierarchies solely because object-oriented inheritance syntax is available; the type graph should clarify the domain, not imitate runtime class structure unnecessarily.
