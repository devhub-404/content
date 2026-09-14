# Classes, Fields, and Properties

Classes are reference types that combine state and behavior. Fields store implementation state, while properties expose value-like access through getters and setters and can be auto-implemented or backed by custom logic. Access modifiers define the supported visibility boundary.

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

Keep invariants behind methods and properties rather than exposing mutable fields. A property should behave like inexpensive value access; expensive work or actions with visible side effects are usually clearer as methods.
