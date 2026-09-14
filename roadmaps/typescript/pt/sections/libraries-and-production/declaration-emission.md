# Emissão de Declarations

Builds de biblioteca podem emitir `.d.ts` a partir do source TypeScript com `declaration`. Declaration maps conectam definições publicadas ao source para navegação no editor. `emitDeclarationOnly` é útil quando outra ferramenta emite JavaScript mas TypeScript ainda possui os artefatos públicos de tipos.

```ts
{
  "compilerOptions": {
    "declaration": true,
    "declarationMap": true,
    "emitDeclarationOnly": true,
    "outDir": "./dist"
  }
}
```

Inspecione declarations geradas como consumidor. Detalhes inferidos internos podem vazar em assinaturas públicas, dependências podem virar imports obrigatórios de tipos e nomes internos inacessíveis podem tornar output inutilizável. Anotações explícitas estáveis nas fronteiras exportadas normalmente produzem declarations mais limpas e previsíveis.
