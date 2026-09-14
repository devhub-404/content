# Statements, expresiones y comentarios

Una expresión produce un valor: un literal, una operación, una llamada, un acceso a propiedad o una expresión condicional. Un statement realiza una acción del lenguaje como declarar un binding, ramificar, iterar, retornar o lanzar un error. Las expresiones aparecen con frecuencia dentro de statements.

```js
const price = 12;
const total = price * 3;

if (total > 30) {
  console.log("Large order");
}
```

Los comentarios usan `//` para una línea y `/* ... */` para un bloque. Deben explicar intención, restricciones o decisiones poco obvias, no repetir lo que el código ya dice. JavaScript puede insertar punto y coma automáticamente en casos definidos, pero un formatter consistente y una sintaxis clara evitan depender de reglas difíciles de recordar.
