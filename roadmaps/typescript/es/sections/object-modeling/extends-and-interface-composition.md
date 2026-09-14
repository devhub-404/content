# Extensión de interfaces y composición de objetos

Una interface puede extender uno o más object types y crear un contrato nombrado con todos sus miembros. Es una relación de tipos: no crea herencia de prototypes en runtime. Un objeto simple puede satisfacer la interface sin ser instancia de ninguna clase.

```ts
interface Entity {
  id: string;
}

interface User extends Entity {
  name: string;
}

interface Admin extends User {
  permissions: string[];
}
```

Usa `extends` cuando el subtipo sea una relación estable y legible. Para transformaciones puntuales, unions o intersections pueden expresar mejor la idea. No construyas jerarquías profundas solo porque la sintaxis se parezca a OOP tradicional.
