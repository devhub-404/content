# `Span<T>`, `Memory<T>` e Código Allocation-aware

`Span<T>` e `ReadOnlySpan<T>` são views stack-only sobre memória contígua e podem apontar para arrays, stack allocations, strings ou buffers unmanaged. `Memory<T>` oferece views relacionadas que podem ser armazenadas e atravessar async boundaries.

```csharp
static int CountCommas(ReadOnlySpan<char> text)
{
    int count = 0;
    foreach (char c in text)
        if (c == ',') count++;
    return count;
}
```

Esses tipos evitam cópias/allocations em hot paths, mas adicionam complexidade de lifetime e API. Use arrays/strings comuns até medições ou design de library mostrarem benefício real.
