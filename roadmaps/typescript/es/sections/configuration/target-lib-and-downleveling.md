# `target`, `lib` y downleveling

`target` controla qué sintaxis JavaScript puede transformar TypeScript cuando emite código. `lib` controla qué declarations de APIs y built-ins están disponibles al checker. Incluir un tipo en `lib` no polyfillea esa API en runtime.

```ts
{
  "compilerOptions": {
    "target": "ES2024",
    "lib": ["ES2024", "DOM"]
  }
}
```

TypeScript puede downlevel parte de la sintaxis, pero no añade automáticamente todos los built-ins que falten. Estos necesitan un runtime compatible o polyfill. Elige el target según el entorno de despliegue real, no según un valor heredado de otra configuración.
