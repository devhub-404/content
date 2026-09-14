# Project References

Project references dividem codebase grande em projetos TypeScript com relações explícitas de dependência. Projetos referenciados usam `composite` e podem produzir declarations/build info permitindo a `tsc --build` verificar e reconstruir apenas partes necessárias.

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

São úteis em monorepos e bibliotecas grandes onde um projeto gigante fica lento ou fronteiras precisam de enforcement. Não adicione references apenas porque repositório possui pastas; o grafo deve refletir limites reais de pacote/build. Alinhe referências TypeScript com grafos do package manager e runtime para evitar duas arquiteturas conflitantes.
