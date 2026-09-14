# Fundamentos de `tsconfig.json`

Um `tsconfig.json` marca projeto TypeScript e define arquivos raiz mais comportamento do compilador. `include`, `exclude` e `files` controlam o grafo do projeto, enquanto `compilerOptions` configura checking, libraries da linguagem, módulos, interoperabilidade e output.

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

Não copie configuração sem entender o runtime e build tool modelados. `target`, `lib`, `module` e `moduleResolution` respondem perguntas diferentes. TypeScript 6.0 mudou vários defaults e deprecou opções antigas, então templates atuais são ponto de partida mais seguro que configs copiadas de tutoriais antigos.
