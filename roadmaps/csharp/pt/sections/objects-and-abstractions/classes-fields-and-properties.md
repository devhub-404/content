# Classes, Fields e Properties

Classes são reference types que combinam estado e comportamento. Fields armazenam implementação, enquanto properties expõem acesso semelhante a valor por getters/setters e podem ser automáticas ou customizadas. Access modifiers definem visibility.

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

Mantenha invariantes atrás de métodos/properties em vez de expor fields mutáveis. Property deve parecer acesso de valor barato; trabalho caro ou side effects visíveis ficam mais claros como métodos.
