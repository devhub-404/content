# `target`, `lib`, and Downleveling

`target` controls which JavaScript syntax TypeScript may transform when it emits. `lib` controls which built-in and host API type declarations are available to the checker. They are related but not equivalent: including a type declaration does not polyfill a missing runtime API.

```ts
{
  "compilerOptions": {
    "target": "ES2024",
    "lib": ["ES2024", "DOM"]
  }
}
```

TypeScript can downlevel some syntax, but it does not automatically supply every missing built-in such as newer Array methods or Promise features. Those need an appropriate runtime or polyfill. TypeScript 6.0 deprecates `target: es5`, reflecting the increasingly modern baseline of supported tooling; choose a target from the actual deployment environment.
