# Methods, `this`, `bind`, `call`, and `apply`

For ordinary functions, `this` is usually determined by the call form. `account.deposit()` uses `account` as the receiver; extracting the method and calling it by itself loses that receiver in normal strict code. `bind()` creates a new function with a fixed receiver and optionally pre-filled arguments.

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

`call()` and `apply()` invoke immediately with an explicit receiver; the difference is how arguments are supplied. Arrow functions capture lexical `this` instead. If a function does not conceptually operate on a receiver, pass data explicitly rather than designing a surprising binding requirement. Clear ownership beats clever `this` manipulation.
