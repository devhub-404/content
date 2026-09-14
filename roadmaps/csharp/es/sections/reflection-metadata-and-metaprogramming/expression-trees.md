# Expression Trees

Un expression tree representa código como datos en vez de solo comportamiento ejecutable de un delegate. Los providers LINQ pueden inspeccionarlo y traducir operaciones a otro lenguaje, como SQL, y otras herramientas pueden analizar o transformar expresiones.

```csharp
Expression<Func<User, bool>> filter =
    user => user.IsActive && user.Age >= 18;

Console.WriteLine(filter);
```

No toda expresión C# puede representarse o traducirse por cualquier provider. Al usar `IQueryable<T>`, comprueba soporte y no supongas que métodos .NET arbitrarios podrán ejecutarse remotamente.
