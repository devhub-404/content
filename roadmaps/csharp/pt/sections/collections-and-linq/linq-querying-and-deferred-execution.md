# Queries LINQ e Deferred Execution

LINQ fornece vocabulário comum para filter, projection, ordering, grouping, joins e aggregations. A maioria dos operators sobre `IEnumerable<T>` usa deferred execution: a query só roda na enumeração.

```csharp
var activeNames = users
    .Where(user => user.IsActive)
    .OrderBy(user => user.Name)
    .Select(user => user.Name);

foreach (string name in activeNames)
{
    Console.WriteLine(name);
}
```

Materialize com `ToList`/`ToArray` quando precisa snapshot ou traversal estável repetido. Saiba se a fonte é `IEnumerable<T>` in-memory ou `IQueryable<T>` de provider, porque operações suportadas e custos podem mudar muito.
