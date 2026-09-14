# Inheritance, Virtual, and Abstract Members

Classes support single class inheritance and polymorphic dispatch through `virtual`, `abstract`, and `override`. An abstract class can share implementation and state while requiring derived classes to provide selected members. `sealed` can prevent further inheritance or overriding.

```csharp
public abstract class Shape
{
    public abstract double Area { get; }
}

public sealed class Circle(double radius) : Shape
{
    public override double Area => Math.PI * radius * radius;
}
```

Use inheritance for genuine substitutability, not just code reuse. Deep hierarchies make state and lifecycle harder to understand; composition and interfaces are often better when one type merely uses another capability.
