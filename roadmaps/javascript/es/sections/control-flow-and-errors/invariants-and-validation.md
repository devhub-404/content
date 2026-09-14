# Invariantes del programa y validación

Una invariante es una condición que debe ser verdadera para que el código posterior tenga sentido. JavaScript no posee un statement de assertion específico para lógica de aplicación, por lo que checks normales y errores suelen ser la forma más clara de imponer precondiciones y estados imposibles.

```js
function transfer(amount) {
  if (!Number.isFinite(amount) || amount <= 0) {
    throw new RangeError("amount must be a positive finite number");
  }

  // Later code can rely on the invariant.
}
```

Valida datos externos en las fronteras del sistema y deja que el código interno dependa de la forma ya validada. `console.assert()` es diagnóstico, no un contrato fiable de control de flujo. Un error útil falla cerca de la suposición violada y aporta suficiente contexto para actuar.
