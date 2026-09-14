# Promises and Chaining

A Promise represents the eventual completion or failure of an asynchronous operation. It begins pending and later becomes fulfilled with a value or rejected with a reason. `then()` registers handlers and returns a new promise, which allows a chain to describe dependent asynchronous steps.

```js
loadUser()
  .then(user => loadOrders(user.id))
  .then(orders => renderOrders(orders))
  .catch(error => showError(error))
  .finally(() => stopSpinner());
```

A value returned from a handler fulfills the next promise, a returned promise is adopted, and a thrown error rejects the next promise. `catch()` handles rejections and `finally()` runs cleanup-like work without normally replacing the original outcome. Return asynchronous work from handlers whenever later steps depend on it; otherwise the chain can continue too early.
