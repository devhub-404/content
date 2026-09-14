# Project references

Project references dividen una base grande en varios proyectos TypeScript con dependencias explícitas. Los proyectos referenciados usan `composite` y `tsc --build` puede comprobar y reconstruir solo las partes necesarias.

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

Son útiles en monorepos y librerías grandes cuando las fronteras reales coinciden con paquetes o builds. No añadas references solo porque hay varias carpetas. Alinea el grafo TypeScript con las dependencias reales del workspace y del runtime.
