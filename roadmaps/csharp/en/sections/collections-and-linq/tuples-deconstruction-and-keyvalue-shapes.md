# Tuples and Deconstruction

Value tuples provide lightweight grouped values with optional element names, and deconstruction assigns their components into separate variables. Classes, records, and custom types can also participate in deconstruction through suitable `Deconstruct` methods.

```csharp
static (int Min, int Max) Bounds(IEnumerable<int> values)
{
    return (values.Min(), values.Max());
}

var (min, max) = Bounds([3, 8, 2]);
```

Tuples work well for small local results whose elements have an obvious relationship. When the shape crosses a public boundary, grows many fields, or needs behavior and validation, a named record or struct usually communicates the contract better.
