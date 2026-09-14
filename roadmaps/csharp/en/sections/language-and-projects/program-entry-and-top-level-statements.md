# Program Entry and Top-level Statements

A console application can use top-level statements instead of writing an explicit `Program.Main`. The compiler still creates an entry point, and command-line arguments are available through the implicit `args` variable. Traditional `static void Main` or `static Task Main` remains valid when an explicit entry type is useful.

```csharp
string name = args.Length > 0 ? args[0] : "world";
Console.WriteLine($"Hello, {name}");
```

Top-level statements are convenient for small programs and examples, but larger applications still benefit from ordinary types and methods. Do not place the entire application in one top-level file just because the syntax permits it.
