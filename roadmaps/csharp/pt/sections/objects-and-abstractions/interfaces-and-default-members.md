# Interfaces e Default Members

Interfaces descrevem capacidades sem exigir base class comum. Um tipo pode implementar várias interfaces, e interfaces modernas podem fornecer implementações default. Consumers normalmente dependem de interfaces pequenas enquanto producers retornam tipos concretos.

```csharp
public interface IClock
{
    DateTimeOffset Now { get; }

    bool IsPast(DateTimeOffset value) =>
        value < Now;
}
```

Defina interfaces pelo comportamento necessário ao caller, não como espelho de toda class. Default interface members ajudam evolução de API, mas lógica stateful pesada ainda pertence a tipos comuns.
