# Task Composition and Concurrency

Independent asynchronous operations can start before either is awaited and then be composed with `Task.WhenAll`, `WhenAny`, or ordinary awaits. This enables I/O concurrency without creating one thread per operation.

```csharp
Task<User> userTask = LoadUserAsync(id);
Task<Order[]> ordersTask = LoadOrdersAsync(id);

await Task.WhenAll(userTask, ordersTask);

User user = await userTask;
Order[] orders = await ordersTask;
```

Do not accidentally serialize independent work by awaiting the first operation before starting the second. Conversely, avoid launching unbounded tasks over huge inputs; concurrency limits and backpressure are part of production design.
