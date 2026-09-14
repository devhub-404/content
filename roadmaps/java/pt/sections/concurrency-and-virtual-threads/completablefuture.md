# `CompletableFuture`

`CompletableFuture` representa completion assíncrona e suporta stages dependentes, combinação, recovery e executor explícito. É útil para APIs nonblocking e libraries assíncronas.

```java
CompletableFuture<User> user = loadUser(id);
CompletableFuture<Orders> orders = loadOrders(id);

CompletableFuture<Summary> summary = user.thenCombine(
    orders,
    Summary::new);
```

Chains podem ficar difíceis com error handling/executors. Virtual threads frequentemente deixam workflows blocking-style mais simples; escolha o modelo adequado à API e não misture sem necessidade.
