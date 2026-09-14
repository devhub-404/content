# Interfaces and Default Members

Interfaces describe capabilities without requiring a shared base class. A type can implement many interfaces, and modern interfaces can provide default implementations for selected members. Consumers commonly depend on small interfaces while producers return concrete types.

```csharp
public interface IClock
{
    DateTimeOffset Now { get; }

    bool IsPast(DateTimeOffset value) =>
        value < Now;
}
```

Define interfaces around behavior a caller needs, not as a mirror of every class. Default interface members are useful for API evolution and shared behavior, but heavy stateful logic still belongs in ordinary types.
