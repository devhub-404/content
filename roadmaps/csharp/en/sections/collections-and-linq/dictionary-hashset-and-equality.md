# Dictionary, HashSet, and Equality

`Dictionary<TKey,TValue>` maps unique keys to values, while `HashSet<T>` stores unique values. Both depend on equality and hashing semantics and can accept an `IEqualityComparer<T>` when domain equality differs from the type default.

```csharp
var counts = new Dictionary<string, int>(
    StringComparer.OrdinalIgnoreCase);

counts["rust"] = 2;

var tags = new HashSet<string> { "csharp", "dotnet" };
```

Use `TryGetValue` when missing keys are expected and choose string comparers deliberately for identifiers, paths, or user-facing text. A mutable key whose equality or hash changes while stored can make a hash collection behave incorrectly.
