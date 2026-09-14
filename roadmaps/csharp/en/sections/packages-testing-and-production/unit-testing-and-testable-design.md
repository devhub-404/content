# Unit Testing and Testable Design

.NET test projects can use frameworks such as xUnit, NUnit, or MSTest while `dotnet test` provides a common execution workflow. Good unit tests isolate a behavior, arrange only required state, execute the operation, and assert the externally meaningful result.

```csharp
[Fact]
public void Add_sums_two_values()
{
    var calculator = new Calculator();

    int result = calculator.Add(2, 3);

    Assert.Equal(5, result);
}
```

Design for testability through clear dependencies and small contracts rather than making every method virtual or exposing internals solely for tests. Integration tests remain necessary for databases, files, HTTP, serialization, and framework configuration that mocks cannot verify.
