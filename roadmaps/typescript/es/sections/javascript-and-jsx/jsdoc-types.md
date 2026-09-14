# Tipos TypeScript en JSDoc

JavaScript comprobado puede expresar parámetros, retornos, object shapes, generics, imports y otros contratos mediante JSDoc. Es útil para bibliotecas que desean conservar source `.js` o para proyectos en transición.

```ts
/**
 * @template T
 * @param {T[]} items
 * @returns {T | undefined}
 */
export function first(items) {
  return items[0];
}
```

JSDoc y `.ts` usan el mismo checker, aunque con ergonomía y algunas capacidades distintas. No conviertas cada línea en un comentario de tipos: anota contratos que la inferencia no puede recuperar, sobre todo APIs públicas y fronteras externas.
