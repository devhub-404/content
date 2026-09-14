# Extension Methods and Extension Members

Extension methods let static methods appear in instance-call syntax when the receiver type matches. C# 14 also adds extension blocks for richer extension members, including extension properties and static extensions. The original type is not modified and normal instance members still win name lookup.

```csharp
public static class TextExtensions
{
    public static bool IsBlank(this string? value) =>
        string.IsNullOrWhiteSpace(value);
}

if (input.IsBlank())
{
    Console.WriteLine("empty");
}
```

Use extensions to add cohesive operations around types you do not own or to keep helper behavior discoverable. Avoid giant extension buckets that make every type appear to have unrelated methods.
