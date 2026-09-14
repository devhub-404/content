# Objetos y propiedades

Los objetos son colecciones mutables de propiedades cuyas claves son strings o symbols. Los object literals permiten crear propiedades normales o computadas, y el acceso puede hacerse con punto o con brackets cuando la clave es dinámica.

```js
const field = "email";

const user = {
  id: 42,
  name: "Mina",
  [field]: "mina@example.com",
};

console.log(user.name);
console.log(user["email"]);
```

Leer una propiedad ausente suele producir `undefined` tras buscar por la prototype chain. Assignment crea o actualiza propiedades y `delete` elimina propiedades propias configurables. Usa `Object.hasOwn()` cuando necesites distinguir una propiedad propia de una heredada.
