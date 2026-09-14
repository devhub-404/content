# Reflection e Type Metadata

Reflection inspeciona assemblies, tipos, members, generic arguments e attributes, e pode construir/invocar dinamicamente. Ela sustenta serializers, DI containers, test frameworks, plugins e tooling.

```csharp
Type type = typeof(User);

foreach (PropertyInfo property in type.GetProperties())
{
    Console.WriteLine(property.Name);
}
```

Reflection troca garantias de compile time e speed por flexibilidade runtime. Cache metadata repetida, valide members descobertos e prefira generics ou generated code quando os tipos são conhecidos em compile time.
