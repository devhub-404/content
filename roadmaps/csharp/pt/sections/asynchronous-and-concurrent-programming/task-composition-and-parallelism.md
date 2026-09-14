# Composição de Tasks e Concorrência

Operações assíncronas independentes podem começar antes de qualquer `await` e depois ser combinadas com `Task.WhenAll`, `WhenAny` ou awaits comuns. Isso permite concorrência de I/O sem um thread por operação.

```csharp
Task<User> userTask = LoadUserAsync(id);
Task<Order[]> ordersTask = LoadOrdersAsync(id);

await Task.WhenAll(userTask, ordersTask);

User user = await userTask;
Order[] orders = await ordersTask;
```

Não serialize trabalho independente esperando o primeiro antes de iniciar o segundo. Também evite lançar tasks sem limite sobre inputs enormes; limits e backpressure fazem parte do design de produção.
