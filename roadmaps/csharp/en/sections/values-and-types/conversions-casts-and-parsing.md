# Conversions, Casts, and Parsing

C# distinguishes implicit conversions that are considered safe enough from explicit conversions that require a cast. Numeric narrowing can lose information, and `checked` can turn integral overflow in supported operations into an exception instead of silent wraparound. Parsing text is a separate operation from casting values.

```csharp
int count = 42;
long wide = count;           // implicit
int narrow = checked((int)wide);

if (int.TryParse("123", out int value))
{
    Console.WriteLine(value);
}
```

At external boundaries prefer `TryParse`, validation, or explicit conversion APIs over exceptions for ordinary invalid input. A cast should state a real type relationship or numeric policy, not simply silence the compiler.
