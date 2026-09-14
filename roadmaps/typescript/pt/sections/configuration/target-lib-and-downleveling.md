# `target`, `lib` e Downleveling

`target` controla qual sintaxe JavaScript o TypeScript pode transformar ao emitir. `lib` controla quais declarations de built-ins e APIs de host ficam disponíveis ao checker. São relacionados, mas não equivalentes: incluir declaration não polyfill uma API ausente no runtime.

```ts
{
  "compilerOptions": {
    "target": "ES2024",
    "lib": ["ES2024", "DOM"]
  }
}
```

TypeScript consegue downlevel de parte da sintaxe, mas não fornece automaticamente todo built-in ausente como métodos novos de Array ou features de Promise. Isso exige runtime adequado ou polyfill. TypeScript 6.0 deprecia `target: es5`, refletindo baseline cada vez mais moderno; escolha target conforme ambiente real de deploy.
