# Attributes

Attributes anexam metadata declarativa a assemblies, tipos, members, parâmetros e outros elementos. Frameworks usam para serialization, routing, testing, interop e convenções. Custom attributes derivam de `Attribute`.

```csharp
[Obsolete("Use NewApi instead")]
public void OldApi() { }

[AttributeUsage(AttributeTargets.Class)]
public sealed class FeatureAttribute : Attribute
{
    public FeatureAttribute(string name) => Name = name;
    public string Name { get; }
}
```

Attributes apenas descrevem metadata; não executam nada sozinhos sem compiler/runtime/framework/analyzer que os leia. Prefira APIs tipadas normais quando o comportamento deve ser evidente por chamadas diretas.
