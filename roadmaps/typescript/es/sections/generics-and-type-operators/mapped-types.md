# Mapped types

Un mapped type recorre una union de claves—normalmente `keyof T`—para construir un nuevo object type. Puede añadir o quitar `readonly` y optional y también remapear claves con `as`.

```ts
type Flags<T> = {
  [K in keyof T]: boolean;
};

type Mutable<T> = {
  -readonly [K in keyof T]-?: T[K];
};
```

Son ideales para transformaciones sistemáticas como «mismas claves, otros valores» o «todas las propiedades opcionales». Pon nombres a las transformaciones importantes; demasiadas capas de mapped y conditional types pueden producir errores difíciles de entender.
