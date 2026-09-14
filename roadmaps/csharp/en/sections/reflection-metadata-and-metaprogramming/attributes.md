# Attributes

Attributes attach declarative metadata to assemblies, types, members, parameters, and other program elements. Frameworks use them for serialization, routing, testing, interop, analyzers, and many other conventions. Custom attributes derive from `Attribute`.

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

Attributes describe metadata; they do nothing by themselves unless a compiler, runtime, framework, analyzer, or your own code reads them. Prefer normal typed APIs when behavior should be obvious from direct calls rather than hidden convention.
