# Records and Value-like Data

Record classes and record structs provide concise syntax for data-oriented types with generated value-based equality, printing, and non-destructive mutation through `with`. Positional records can also generate properties and deconstruction support.

```csharp
public record User(string Name, string Email);

var a = new User("Mina", "m@example.com");
var b = a with { Email = "new@example.com" };

Console.WriteLine(a == b);
```

Use records when identity is primarily the contained data rather than object identity and mutation-heavy behavior. Equality still follows the generated member semantics, so mutable members inside a record can make value equality surprising.
