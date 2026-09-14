# Expression Trees

An expression tree represents code as data rather than immediately compiling it only as executable delegate behavior. LINQ providers can inspect these trees and translate operations into another language, such as SQL, while other tools can analyze or transform expressions.

```csharp
Expression<Func<User, bool>> filter =
    user => user.IsActive && user.Age >= 18;

Console.WriteLine(filter);
```

Not every C# expression can be represented in every expression-tree version or translated by a provider. When using `IQueryable<T>`, verify provider support and avoid assuming that arbitrary .NET methods can execute remotely.
