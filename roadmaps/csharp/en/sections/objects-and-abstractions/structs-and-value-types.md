# Structs and Value Types

Structs are value types. Assignment, parameter passing, and collection storage normally copy their value representation unless a reference modifier is involved. Small immutable values such as coordinates, IDs, and numeric wrappers are common struct candidates.

```csharp
public readonly struct Point
{
    public double X { get; }
    public double Y { get; }

    public Point(double x, double y) =>
        (X, Y) = (x, y);
}
```

Large mutable structs are difficult because copies may be hidden and mutations can affect only a copy. Prefer readonly structs for value objects, and choose a class when shared identity or extensive mutable state is central.
