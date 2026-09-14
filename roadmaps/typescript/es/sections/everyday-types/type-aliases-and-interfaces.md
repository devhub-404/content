# Type aliases e interfaces

Type aliases e interfaces pueden describir object shapes. Las interfaces están orientadas a contratos de objetos y admiten `extends` y declaration merging; los aliases pueden nombrar cualquier expresión de tipo, incluidos unions, tuples, primitives, mapped y conditional types.

```ts
type Point = {
  x: number;
  y: number;
};

interface User {
  id: string;
  name: string;
}
```

Para objetos normales, ambas opciones pueden ser correctas. Usa interface cuando quieras un contrato de objeto abierto o extensible y alias cuando necesites componer expresiones arbitrarias. Ninguna de las dos crea un constructor o validador en runtime.
