# Funciones y valores de retorno

Las funciones son objetos invocables. Una function declaration crea un binding con nombre que se inicializa al preparar el scope; una function expression crea una función como valor que puede asignarse o pasarse. Cada llamada crea su propio contexto local.

```js
function add(a, b) {
  return a + b;
}

const multiply = function (a, b) {
  return a * b;
};
```

`return` termina la invocación y entrega un resultado; llegar al final sin retornar un valor produce `undefined`. Los nombres de función ayudan en stack traces y recursión. Prefiere funciones con inputs, outputs y efectos claros, sin dividir mecánicamente lógica simple en helpers que no añaden comprensión.
