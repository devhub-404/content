# Dictionary, HashSet e Equality

`Dictionary<TKey,TValue>` mapeia chaves únicas para valores e `HashSet<T>` armazena valores únicos. Ambos dependem de equality/hash e aceitam `IEqualityComparer<T>` quando a igualdade de domínio difere do default.

```csharp
var counts = new Dictionary<string, int>(
    StringComparer.OrdinalIgnoreCase);

counts["rust"] = 2;

var tags = new HashSet<string> { "csharp", "dotnet" };
```

Use `TryGetValue` quando chave ausente é normal e escolha string comparer deliberadamente. Uma chave mutável cujo hash/equality muda enquanto armazenada pode quebrar a collection.
