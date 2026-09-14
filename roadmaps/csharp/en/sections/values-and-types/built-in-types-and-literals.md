# Built-in Types and Literals

C# has integral, floating-point, decimal, Boolean, character, string, object, and other built-in aliases for .NET types. Numeric literals support suffixes, digit separators, hexadecimal, and binary forms. `decimal` is base-10-oriented and is commonly preferred for financial quantities where decimal rounding is part of the domain.

```csharp
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
decimal price = 19.99m;
bool ready = true;
char letter = 'A';
```

Pick a type from the domain and API contract, not from habit. `int` is the normal general-purpose integer, but IDs, timestamps, money, and protocol fields may deserve different types or domain wrappers.
