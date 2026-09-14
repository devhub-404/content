# `using` e Disposal Explícito

Uma declaração `using` vincula recurso disposable e chama automaticamente `[Symbol.dispose]()` quando o escopo léxico termina. Cleanup ocorre em conclusão normal e saídas abruptas como erro, return, break ou continue. Vários recursos no mesmo escopo são descartados em ordem inversa à declaração.

```js
class Lock {
  acquire() {
    console.log("locked");
    return this;
  }

  [Symbol.dispose]() {
    console.log("unlocked");
  }
}

{
  using lock = new Lock().acquire();
  // protected work
}
```

Isso é gerenciamento explícito para locks, handles, subscriptions ou outros recursos cujo lifetime externo importa; não substitui garbage collection. O recurso precisa implementar protocolo disposable, embora valores nullish sejam permitidos. Binding `using` não pode ser reatribuído, e ownership continua importante se outra referência ao objeto descartado escapar do escopo.
