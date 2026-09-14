# `typeof` en posiciones de tipo

El `typeof` del type system obtiene el tipo estático de un valor o propiedad existente. Comparte el nombre con el operador JavaScript de runtime, pero cumple otra función y solo aparece donde se espera un tipo.

```ts
const defaults = {
  retries: 3,
  mode: "safe" as const,
};

type Defaults = typeof defaults;

function configure(options: Partial<Defaults>) {
  // ...
}
```

Es útil cuando el valor debe ser la fuente de verdad y quieres derivar tipos en vez de duplicar una forma. Está limitado a identificadores y accesos de propiedad razonables, lo que mantiene la extracción predecible.
