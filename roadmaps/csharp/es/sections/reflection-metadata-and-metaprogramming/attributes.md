# Attributes

Los attributes adjuntan metadata declarativa a assemblies, tipos, members, parámetros y otros elementos. Los frameworks los usan para serialización, routing, testing, interop y convenciones. Los custom attributes derivan de `Attribute`.

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

Los attributes solo describen metadata; no hacen nada por sí mismos sin compiler/runtime/framework/analyzer que los lea. Prefiere APIs tipadas normales cuando el comportamiento deba ser evidente mediante llamadas directas.
