# `tsconfig.json` Basics

A `tsconfig.json` marks a TypeScript project and defines root files plus compiler behavior. `include`, `exclude`, and `files` control the project graph, while `compilerOptions` configures checking, language libraries, modules, interoperability, and output.

```ts
{
  "compilerOptions": {
    "strict": true,
    "target": "ES2024",
    "module": "nodenext",
    "moduleResolution": "nodenext",
    "noEmit": true
  },
  "include": ["src"]
}
```

Do not copy a configuration without knowing the runtime and build tool it models. `target`, `lib`, `module`, and `moduleResolution` answer different questions. TypeScript 6.0 changed several defaults and deprecated old options, so current templates are safer starting points than configuration copied from years-old tutorials.
