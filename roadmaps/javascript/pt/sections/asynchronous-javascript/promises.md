# Promises e Encadeamento

Promise representa conclusão ou falha futura de operação assíncrona. Começa pending e depois fica fulfilled com valor ou rejected com motivo. `then()` registra handlers e retorna nova promise, permitindo que uma chain descreva passos assíncronos dependentes.

```js
loadUser()
  .then(user => loadOrders(user.id))
  .then(orders => renderOrders(orders))
  .catch(error => showError(error))
  .finally(() => stopSpinner());
```

Valor retornado por handler fulfill a próxima promise, promise retornada é adotada e erro lançado rejeita a próxima. `catch()` trata rejections e `finally()` executa trabalho semelhante a cleanup sem normalmente substituir o resultado original. Retorne trabalho assíncrono dos handlers sempre que passos posteriores dependerem dele; caso contrário a chain pode continuar cedo demais.
