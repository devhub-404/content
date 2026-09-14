# Operadores, short-circuit y optional chaining

JavaScript incluye operadores aritméticos, de asignación, comparación, lógicos, bitwise, condicionales y de acceso. `&&` y `||` hacen short-circuit y devuelven uno de sus operandos; el operador condicional elige entre dos valores dentro de una expresión.

```js
const canEdit = signedIn && permissions.includes("edit");
const label = compact ? "Save" : "Save changes";
const city = user.address?.city ?? "Unknown";

settings.theme ??= "system";
```

Optional chaining `?.` detiene un acceso o llamada cuando la base es nullish y `??` proporciona fallback solo para null/undefined. Los operadores de asignación lógica combinan esas reglas con assignment. Usa paréntesis cuando varias familias de operadores hagan que la agrupación no sea inmediatamente obvia.
