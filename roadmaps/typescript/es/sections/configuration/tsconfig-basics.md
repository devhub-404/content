# Fundamentos de `tsconfig.json`

`tsconfig.json` define un proyecto TypeScript: qué archivos forman parte y cómo debe comportarse el compilador. `files`, `include` y `exclude` controlan el grafo; `compilerOptions` configura checking, librerías, módulos, interoperabilidad y emisión.

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

No copies una configuración sin saber qué runtime y build tool modela. `target`, `lib`, `module` y `moduleResolution` responden preguntas diferentes. Usa templates actuales del entorno y revisa cada opción que cambie el contrato del proyecto.
