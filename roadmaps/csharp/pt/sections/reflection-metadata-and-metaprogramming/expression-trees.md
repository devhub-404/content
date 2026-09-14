# Expression Trees

Expression tree representa código como dados em vez de apenas delegate executável. Providers LINQ podem inspecionar a árvore e traduzir operações para outra linguagem, como SQL, enquanto ferramentas podem analisar ou transformar expressões.

```csharp
Expression<Func<User, bool>> filter =
    user => user.IsActive && user.Age >= 18;

Console.WriteLine(filter);
```

Nem toda expressão C# pode ser representada ou traduzida por qualquer provider. Ao usar `IQueryable<T>`, verifique suporte e não presuma que métodos .NET arbitrários executarão remotamente.
