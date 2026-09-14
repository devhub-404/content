# Generic Types and Constraints

Generics let types and methods preserve static type relationships without casting or `object`. Constraints such as `class`, `struct`, `notnull`, base types, interfaces, constructor requirements, and newer generic-math interfaces tell generic code which operations are valid.

```csharp
public sealed class Repository<T>
    where T : class
{
    private readonly List<T> _items = [];

    public void Add(T item) => _items.Add(item);
}
```

Add only constraints the implementation truly needs. A generic parameter that appears once and preserves no relationship may not add value. Generic collections and algorithms are strongest when the type parameter connects inputs, outputs, and stored values.
