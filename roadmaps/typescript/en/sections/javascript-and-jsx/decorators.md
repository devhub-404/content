# Standard Decorators

Modern TypeScript supports the standardized decorators model introduced in TypeScript 5.0. A decorator receives the decorated value and a context object and can observe, replace, or initialize supported class elements according to the proposal's semantics.

```ts
function logged(
  original: (this: any, ...args: any[]) => any,
  context: ClassMethodDecoratorContext
) {
  return function (this: any, ...args: any[]) {
    console.log(`calling ${String(context.name)}`);
    return original.call(this, ...args);
  };
}

class Service {
  @logged
  run() {}
}
```

This model is different from TypeScript's older experimental decorator system and its metadata conventions. Libraries must state which model they require. Decorators are powerful metaprogramming and can hide control flow, so use them where a framework or cross-cutting abstraction benefits enough to justify the indirection.
