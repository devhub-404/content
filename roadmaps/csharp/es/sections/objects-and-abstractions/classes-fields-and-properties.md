# Classes, Fields y Properties

Las classes son reference types que combinan estado y comportamiento. Los fields almacenan implementación, mientras las properties exponen acceso similar a un valor mediante getters/setters y pueden ser automáticas o personalizadas. Los access modifiers definen visibility.

```csharp
public sealed class Account
{
    private decimal _balance;

    public string Owner { get; }
    public decimal Balance => _balance;

    public Account(string owner)
    {
        Owner = owner;
    }
}
```

Mantén invariantes detrás de métodos/properties en vez de exponer fields mutables. Una property debería parecer acceso de valor barato; trabajo costoso o side effects visibles son más claros como métodos.
