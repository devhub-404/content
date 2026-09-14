# `Span<T>`, `Memory<T>`, and Allocation-aware Code

`Span<T>` and `ReadOnlySpan<T>` are stack-only views over contiguous memory and can point into arrays, stack allocations, strings, or unmanaged buffers. `Memory<T>` and `ReadOnlyMemory<T>` provide related heap-storable views that can cross async boundaries.

```csharp
static int CountCommas(ReadOnlySpan<char> text)
{
    int count = 0;
    foreach (char c in text)
        if (c == ',') count++;
    return count;
}
```

These types are performance tools for avoiding copies and temporary allocations in hot paths. They add lifetime and API complexity, so use ordinary arrays and strings until measurements or library design show a meaningful benefit.
