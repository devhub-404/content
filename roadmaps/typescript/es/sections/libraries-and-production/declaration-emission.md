# Emisión de declarations

Una librería puede generar `.d.ts` desde el source con `declaration`, añadir declaration maps y usar `emitDeclarationOnly` cuando otra herramienta genera el JavaScript. Así TypeScript sigue siendo responsable del contrato de tipos publicado.

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

Revisa el output como lo haría un consumidor. Inferencia interna puede filtrar tipos no deseados y dependencias pueden aparecer en firmas públicas. Anotaciones explícitas en fronteras exportadas suelen producir declarations más estables y legibles.
