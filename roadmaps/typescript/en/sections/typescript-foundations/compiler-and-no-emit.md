# Type Checking, Emission, and `noEmit`

The TypeScript compiler can both type-check and emit JavaScript, but those jobs can be separated. Many modern projects let another tool transpile or bundle the source and use `tsc --noEmit` only as a typechecker. Other projects use `tsc` to produce JavaScript and declaration files directly.

```ts
{
  "compilerOptions": {
    "strict": true,
    "noEmit": true
  }
}
```

The important question is which tool owns each stage: type checking, syntax transformation, module bundling, minification, and declaration emission. Avoid assuming that a successful transpile means a successful type check. A project can emit JavaScript even with type errors depending on configuration and toolchain, so CI should run the checker deliberately.
