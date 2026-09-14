# Métodos, `this`, `bind`, `call` e `apply`

Para funções comuns, `this` normalmente é determinado pela forma da chamada. `account.deposit()` usa `account` como receiver; extrair o método e chamá-lo sozinho perde esse receiver em código strict normal. `bind()` cria nova função com receiver fixo e opcionalmente argumentos pré-preenchidos.

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

`call()` e `apply()` invocam imediatamente com receiver explícito; a diferença é como os argumentos são fornecidos. Arrow functions capturam `this` léxico. Se uma função não opera conceitualmente sobre receiver, passe dados explicitamente em vez de projetar requisito de binding surpreendente. Ownership claro é melhor que manipulação engenhosa de `this`.
