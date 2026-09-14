# `Span<T>`, `Memory<T>` y Código Allocation-aware

`Span<T>` y `ReadOnlySpan<T>` son views stack-only sobre memoria contigua y pueden apuntar a arrays, stack allocations, strings o buffers unmanaged. `Memory<T>` ofrece views relacionadas que pueden almacenarse y cruzar async boundaries.

```csharp
static int CountCommas(ReadOnlySpan<char> text)
{
    int count = 0;
    foreach (char c in text)
        if (c == ',') count++;
    return count;
}
```

Estos tipos evitan copias/allocations en hot paths, pero añaden complejidad de lifetime y API. Usa arrays/strings normales hasta que mediciones o diseño de library demuestren un beneficio real.
