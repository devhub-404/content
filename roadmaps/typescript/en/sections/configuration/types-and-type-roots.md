# Ambient Type Packages and `types`

Ambient type packages can add globals and declarations to a project, commonly through `@types` packages or package-provided types. The `types` option explicitly chooses which ambient packages are included in the global scope.

```ts
{
  "compilerOptions": {
    "types": ["node", "vitest/globals"]
  }
}
```

TypeScript 6.0 changes `types` to default to an empty list, making ambient type inclusion more explicit. This reduces accidental dependence on unrelated packages installed elsewhere in a workspace. Importable module types still resolve normally; the option is about which packages contribute globals without being explicitly imported.
