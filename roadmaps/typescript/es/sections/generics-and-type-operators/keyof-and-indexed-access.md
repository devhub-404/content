# `keyof` e indexed access types

`keyof T` produce una union con las claves conocidas de un tipo. `T[K]` obtiene el tipo asociado a una clave o grupo de claves. Juntos permiten que APIs genéricas conserven la relación entre la propiedad seleccionada y su valor.

```ts
type User = {
  id: string;
  name: string;
  active: boolean;
};

type UserKey = keyof User;       // "id" | "name" | "active"
type UserName = User["name"];    // string

function get<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
```

Estos operadores existen solo en el type system; `keyof` no inspecciona un objeto en runtime. Cuando una función debe aceptar solo propiedades válidas, `K extends keyof T` suele ser mucho más preciso que un `string` abierto.
