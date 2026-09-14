# Module Settings in TypeScript 6.0

Module configuration is one of the most environment-sensitive parts of TypeScript. Modern Node projects generally use Node-aware module modes; bundler-driven projects often use bundler-oriented resolution. The setting should describe how imports are interpreted by the actual runtime or build system.

```ts
{
  "compilerOptions": {
    "module": "nodenext",
    "moduleResolution": "nodenext",
    "verbatimModuleSyntax": true
  }
}
```

TypeScript 6.0 deprecates several legacy module options, including old `node10`/`classic` resolution and AMD/UMD/SystemJS module emit choices. It also moves defaults toward modern interoperability. New code should not begin with a legacy config merely because an older tutorial used it; start from your runtime's current official template.
