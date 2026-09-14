# Unit Testing y Diseño Testable

Los proyectos de test .NET pueden usar xUnit, NUnit o MSTest mientras `dotnet test` ofrece un workflow común. Los buenos unit tests aíslan un comportamiento, preparan solo el estado necesario, ejecutan y verifican el resultado significativo.

```csharp
[Fact]
public void Add_sums_two_values()
{
    var calculator = new Calculator();

    int result = calculator.Add(2, 3);

    Assert.Equal(5, result);
}
```

Diseña testabilidad con dependencias claras y contratos pequeños en vez de volver todo virtual o exponer internals solo para tests. Los integration tests siguen siendo necesarios para bases de datos, files, HTTP, serialización y configuración de frameworks.
