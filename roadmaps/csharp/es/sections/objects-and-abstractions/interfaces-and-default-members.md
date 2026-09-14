# Interfaces y Default Members

Las interfaces describen capacidades sin exigir una base class común. Un tipo puede implementar varias interfaces y las interfaces modernas pueden proporcionar implementaciones default. Los consumers suelen depender de interfaces pequeñas mientras los producers retornan tipos concretos.

```csharp
public interface IClock
{
    DateTimeOffset Now { get; }

    bool IsPast(DateTimeOffset value) =>
        value < Now;
}
```

Define interfaces por el comportamiento que necesita el caller, no como espejo de cada class. Los default interface members ayudan a evolucionar APIs, pero lógica stateful pesada sigue perteneciendo a tipos normales.
