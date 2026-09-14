# `CompletableFuture`

`CompletableFuture` represents asynchronous completion and supports dependent stages, combination, recovery, and explicit executor selection. It is useful for nonblocking APIs and integration with asynchronous libraries.

```java
CompletableFuture<User> user = loadUser(id);
CompletableFuture<Orders> orders = loadOrders(id);

CompletableFuture<Summary> summary = user.thenCombine(
    orders,
    Summary::new);
```

Chains can become hard to read when exception handling, executor choice, and many branches interact. Virtual-thread code can often express blocking-style workflows more simply, so choose the model that matches the underlying API and operational needs rather than mixing them casually.
