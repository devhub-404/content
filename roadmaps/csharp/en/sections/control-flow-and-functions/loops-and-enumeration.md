# Loops and Enumeration

C# provides `for`, `foreach`, `while`, and `do` loops. `foreach` consumes the enumeration pattern and is the normal choice when you need each element rather than an index. `break` exits a loop, `continue` advances to the next iteration, and `return` leaves the method entirely.

```csharp
foreach (var item in items)
{
    Console.WriteLine(item);
}

for (int i = 0; i < items.Count; i++)
{
    Console.WriteLine($"{i}: {items[i]}");
}
```

Use indexing when position matters or the collection supports efficient indexed access. Do not mutate a collection structurally while its ordinary enumerator is active unless that collection explicitly supports it.
