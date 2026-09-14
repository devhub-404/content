# Reflection and Type Metadata

Reflection inspects assemblies, types, members, generic arguments, attributes, and can dynamically invoke or construct objects. It powers serializers, dependency injection containers, test frameworks, plugin systems, and tooling.

```csharp
Type type = typeof(User);

foreach (PropertyInfo property in type.GetProperties())
{
    Console.WriteLine(property.Name);
}
```

Reflection trades compile-time guarantees and speed for runtime flexibility. Cache repeated metadata lookups, validate dynamically discovered members, and prefer generic or generated code when the type set is known at compile time.
