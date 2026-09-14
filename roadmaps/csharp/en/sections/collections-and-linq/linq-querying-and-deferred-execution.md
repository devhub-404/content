# LINQ Querying and Deferred Execution

LINQ provides a shared vocabulary for filtering, projection, ordering, grouping, joining, aggregation, and other sequence operations. Most operators on `IEnumerable<T>` use deferred execution, building a query that runs when enumerated rather than immediately.

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

Materialize with `ToList`, `ToArray`, or another terminal operation when you need a snapshot or repeated stable traversal. Understand whether your source is in-memory `IEnumerable<T>` or a provider-backed `IQueryable<T>`, because supported operations and execution costs can differ dramatically.
