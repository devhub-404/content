# Unit Testing e Design Testável

Projetos de teste .NET podem usar xUnit, NUnit ou MSTest enquanto `dotnet test` fornece workflow comum. Bons unit tests isolam comportamento, preparam apenas estado necessário, executam e verificam resultado significativo.

```csharp
[Fact]
public void Add_sums_two_values()
{
    var calculator = new Calculator();

    int result = calculator.Add(2, 3);

    Assert.Equal(5, result);
}
```

Designe testabilidade com dependências claras e contratos pequenos em vez de tornar tudo virtual ou expor internals só para testes. Integration tests continuam necessários para banco, files, HTTP, serialization e framework config.
