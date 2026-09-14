# Promises y chaining

Una Promise representa la conclusión o fallo futuro de una operación. Empieza pending y después queda fulfilled con un valor o rejected con un motivo. `then()` registra handlers y devuelve otra promise, lo que permite encadenar operaciones dependientes.

```js
loadUser()
  .then(user => loadOrders(user.id))
  .then(orders => renderOrders(orders))
  .catch(error => showError(error))
  .finally(() => stopSpinner());
```

Un valor retornado por un handler fulfill la promise siguiente; una promise retornada se adopta; un error lanzado rechaza la siguiente. `catch()` maneja rejections y `finally()` ejecuta cleanup-like work sin reemplazar normalmente el resultado original. Devuelve el trabajo async cuando los siguientes pasos dependan de él.
