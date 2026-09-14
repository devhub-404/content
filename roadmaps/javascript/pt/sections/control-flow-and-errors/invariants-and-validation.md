# Invariantes do Programa e Validação

Uma invariante é uma condição que precisa permanecer verdadeira para o código posterior fazer sentido. JavaScript não possui statement de assertion dedicado à aplicação, então checks e erros comuns normalmente são a forma mais clara de impor precondições públicas ou estados internos impossíveis.

```js
function transfer(amount) {
  if (!Number.isFinite(amount) || amount <= 0) {
    throw new RangeError("amount must be a positive finite number");
  }

  // Later code can rely on the invariant.
}
```

Valide dados externos ou não confiáveis nas fronteiras do sistema e depois deixe o código interno depender da forma validada. APIs diagnósticas como `console.assert()` não formam contrato confiável de validação. Uma falha útil acontece perto da suposição violada e fornece contexto suficiente para caller ou desenvolvedor agir.
