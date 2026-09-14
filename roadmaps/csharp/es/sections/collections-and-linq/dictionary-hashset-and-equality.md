# Dictionary, HashSet y Equality

`Dictionary<TKey,TValue>` mapea claves únicas a valores y `HashSet<T>` almacena valores únicos. Ambos dependen de equality/hash y aceptan `IEqualityComparer<T>` cuando la igualdad del dominio difiere del default.

```csharp
var counts = new Dictionary<string, int>(
    StringComparer.OrdinalIgnoreCase);

counts["rust"] = 2;

var tags = new HashSet<string> { "csharp", "dotnet" };
```

Usa `TryGetValue` cuando una clave ausente sea normal y elige string comparer deliberadamente. Una clave mutable cuyo hash/equality cambia mientras está almacenada puede romper la colección.
