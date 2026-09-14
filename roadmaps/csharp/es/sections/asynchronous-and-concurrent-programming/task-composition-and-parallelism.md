# Composición de Tasks y Concurrencia

Las operaciones asíncronas independientes pueden empezar antes de cualquier `await` y luego combinarse con `Task.WhenAll`, `WhenAny` o awaits normales. Esto permite concurrencia de I/O sin un thread por operación.

```csharp
Task<User> userTask = LoadUserAsync(id);
Task<Order[]> ordersTask = LoadOrdersAsync(id);

await Task.WhenAll(userTask, ordersTask);

User user = await userTask;
Order[] orders = await ordersTask;
```

No serialices trabajo independiente esperando el primero antes de iniciar el segundo. Tampoco lances tasks sin límite sobre inputs enormes; los límites y backpressure forman parte del diseño de producción.
