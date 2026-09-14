# What TypeScript Adds to JavaScript

TypeScript is JavaScript with a static type system and tooling layer. It checks programs before they run, can infer many types from ordinary JavaScript syntax, and erases type-only syntax when emitting JavaScript. The runtime still executes JavaScript, so TypeScript does not change fundamental JavaScript behavior.

```ts
function greet(name: string): string {
  return `Hello, ${name}`;
}

greet("Mina");
// greet(42); // type error
```

The typechecker catches classes of mistakes such as calling values incorrectly, accessing missing properties, or passing incompatible data. It cannot prove every runtime fact, and external data is still untrusted until validated. Learn JavaScript semantics first; TypeScript describes and checks those semantics rather than replacing them.
