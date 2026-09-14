# Project References

Project references split a large codebase into TypeScript projects with explicit dependency relationships. Referenced projects use `composite` and can produce declaration/build information that lets `tsc --build` check and rebuild only the necessary parts.

```ts
// packages/core/tsconfig.json
{
  "compilerOptions": {
    "composite": true,
    "declaration": true
  }
}

// root tsconfig.json
{
  "files": [],
  "references": [
    { "path": "./packages/core" },
    { "path": "./apps/web" }
  ]
}
```

They are useful in monorepos and large libraries where one giant project becomes slow or boundaries need enforcement. Do not add references merely because a repository has folders; the graph should reflect actual package/build boundaries. Align TypeScript references with package-manager and runtime dependency graphs to avoid two conflicting architectures.
