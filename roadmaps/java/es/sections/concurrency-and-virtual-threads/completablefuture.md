# `CompletableFuture`

`CompletableFuture` representa completion asíncrona y soporta stages dependientes, combinación, recovery y executor explícito. Es útil para APIs nonblocking y libraries asíncronas.

```java
CompletableFuture<User> user = loadUser(id);
CompletableFuture<Orders> orders = loadOrders(id);

CompletableFuture<Summary> summary = user.thenCombine(
    orders,
    Summary::new);
```

Las chains pueden volverse difíciles con error handling/executors. Los virtual threads a menudo simplifican workflows blocking-style; elige el modelo adecuado a la API y no mezcles sin necesidad.
