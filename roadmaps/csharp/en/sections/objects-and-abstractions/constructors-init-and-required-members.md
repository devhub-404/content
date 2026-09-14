# Constructors, `init`, and Required Members

Constructors establish an initial valid object state. `init` accessors allow properties to be assigned during object initialization but not later through ordinary assignment, while `required` tells callers that a member must be initialized by construction or object initializer.

```csharp
public sealed class User
{
    public required string Name { get; init; }
    public string? Email { get; init; }
}

var user = new User { Name = "Mina" };
```

Use constructors for invariants that must be validated immediately and required/init members for data-style objects where named initialization is clearer. Do not confuse `required` with runtime validation: it is primarily a compiler contract about initialization presence.
