# Transformar, buscar y reducir arrays

`map` transforma cada elemento, `filter` conserva los que cumplen una condición, `find` devuelve el primero que coincide, `findIndex` su índice, `some` pregunta si alguno coincide y `every` si todos lo hacen. Estos métodos expresan patrones de colección de forma directa.

```js
const activeNames = users
  .filter(user => user.active)
  .map(user => user.name);

const admin = users.find(user => user.role === "admin");
const allValid = users.every(user => user.name.length > 0);
const total = prices.reduce((sum, price) => sum + price, 0);
```

`reduce` combina una secuencia en un acumulador y puede expresar muchas operaciones, pero un método específico o un loop con nombre suele ser más legible que un reducer ingenioso. Usa estos métodos cuando hagan obvio el flujo de datos y loops cuando el control de flujo sea más importante.
