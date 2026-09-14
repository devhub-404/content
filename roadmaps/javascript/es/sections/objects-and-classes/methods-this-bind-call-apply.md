# Métodos, `this`, `bind`, `call` y `apply`

En funciones ordinarias, `this` suele depender de cómo se realiza la llamada. `obj.metodo()` usa `obj` como receiver; extraer el método y llamarlo solo pierde ese receiver en código strict. `bind()` crea una nueva función con `this` fijado.

```js
const account = {
  balance: 100,
  deposit(amount) {
    this.balance += amount;
  },
};

const deposit = account.deposit.bind(account);
deposit(25);
```

`call()` y `apply()` invocan inmediatamente con un receiver explícito y se diferencian en cómo reciben argumentos. Las arrows capturan `this` del contexto exterior. Si una función no necesita conceptualmente un receiver, pasar datos explícitamente suele ser más claro que depender de reglas complejas de binding.
