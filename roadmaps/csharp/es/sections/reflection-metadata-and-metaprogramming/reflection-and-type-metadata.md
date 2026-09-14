# Reflection y Type Metadata

Reflection inspecciona assemblies, tipos, members, generic arguments y attributes, y puede construir/invocar dinámicamente. Sustenta serializers, DI containers, test frameworks, plugins y tooling.

```csharp
Type type = typeof(User);

foreach (PropertyInfo property in type.GetProperties())
{
    Console.WriteLine(property.Name);
}
```

Reflection cambia garantías de compile time y velocidad por flexibilidad runtime. Cachea metadata repetida, valida members descubiertos y prefiere generics o generated code cuando los tipos sean conocidos en compile time.
