# Optional, readonly e index signatures

Una propiedad con `?` puede estar ausente. `readonly` impide asignarla mediante esa referencia tipada, pero no congela profundamente el objeto en runtime. Un index signature describe familias de claves que no conoces individualmente al escribir el tipo.

```ts
interface Settings {
  readonly id: string;
  theme?: "light" | "dark";
  [key: `plugin:${string}`]: unknown;
}
```

No uses `[key: string]: any` para silenciar errores de un objeto cuyos campos sí están definidos. Modela claves dinámicas reales con un index signature estrecho y conserva propiedades explícitas para el resto. Con settings estrictos, «ausente» y «presente con `undefined`» pueden ser conceptos distintos.
