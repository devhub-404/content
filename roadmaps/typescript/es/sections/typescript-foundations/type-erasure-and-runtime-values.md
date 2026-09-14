# Type erasure y valores de runtime

Type aliases, interfaces, argumentos genéricos y la mayoría de la sintaxis de tipos no existen en runtime. Ayudan al checker y al editor y luego desaparecen del JavaScript emitido. No puedes preguntar en runtime si un objeto «implementa una interface» porque la interface ya no existe.

```ts
type UserId = string;

interface User {
  id: UserId;
  name: string;
}

const user: User = { id: "u1", name: "Mina" };
console.log(user.name);
```

La validación de runtime necesita mecanismos de runtime: `typeof`, `instanceof`, checks de propiedades, parsers o schemas. Classes y algunos enums producen valores reales; interfaces y aliases no. Mantener separadas la capa de tipos y la de valores evita muchos errores de diseño.
