# Queries LINQ y Deferred Execution

LINQ ofrece un vocabulario común para filter, projection, ordering, grouping, joins y aggregations. La mayoría de operators sobre `IEnumerable<T>` usa deferred execution: la query se ejecuta al enumerarse.

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

Materializa con `ToList`/`ToArray` cuando necesites un snapshot o recorrido estable repetido. Distingue `IEnumerable<T>` en memoria de `IQueryable<T>` de provider, porque las operaciones soportadas y los costes pueden cambiar mucho.
