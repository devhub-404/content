# Structural Typing

TypeScript is primarily structurally typed: compatibility depends on the shape required by a type rather than a declared nominal relationship. A value with at least the required compatible members can often be assigned even if it never explicitly declared that interface.

```ts
interface Named {
  name: string;
}

const value = {
  name: "Mina",
  role: "admin",
};

const named: Named = value;
```

Structural typing fits JavaScript's object model and makes composition flexible, but it also means two conceptually different values with identical structure can be assignable. When domain identity matters, use distinct literal discriminants, private class members, or branded-style types to prevent accidental interchange.
