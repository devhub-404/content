# `as const` y `satisfies`

`as const` conserva literals estrechos y marca miembros de objetos o arrays como readonly en el tipo inferido. Es útil en tablas constantes, discriminants y tuples donde el widening a `string` o array mutable perdería información.

```ts
const routes = {
  home: "/",
  users: "/users",
} as const;

const palette = {
  primary: "#2457d6",
  danger: "#b42318",
} satisfies Record<string, `#${string}`>;
```

`satisfies` comprueba compatibilidad con un tipo objetivo sin reemplazar el tipo específico inferido de la expresión. Funciona muy bien en configuración: valida la forma y conserva literals útiles. Ninguno de los dos congela ni valida el objeto en runtime.
