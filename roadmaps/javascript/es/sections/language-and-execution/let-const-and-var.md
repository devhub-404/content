# `let`, `const` y `var`

Usa `const` cuando el binding no será reasignado y `let` cuando la reasignación forme parte del algoritmo. Ambos tienen scope de bloque y permanecen en temporal dead zone hasta su inicialización. `const` impide cambiar el binding, no modificar el contenido de un objeto almacenado en él.

```js
const taxRate = 0.2;
let total = 100;
total += total * taxRate;

if (total > 100) {
  const message = "Large total";
  console.log(message);
}
```

`var` tiene scope de función, se inicializa como `undefined` durante hoisting y permite redeclaración en el mismo scope. Debes entenderlo porque aparece en código existente, pero código nuevo suele ser más claro con `const` y `let`. Declara los valores cerca del inicio real de su vida útil.
