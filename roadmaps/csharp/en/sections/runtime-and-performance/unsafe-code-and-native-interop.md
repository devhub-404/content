# Unsafe Code and Native Interop

C# can enter an `unsafe` context for pointer arithmetic, fixed memory, and selected interop scenarios. .NET also provides P/Invoke and native interop facilities for calling unmanaged libraries. Unsafe code bypasses some managed safety guarantees and requires explicit project permission.

```csharp
unsafe
{
    int value = 42;
    int* pointer = &value;
    Console.WriteLine(*pointer);
}
```

Keep unsafe boundaries narrow and wrap them in well-tested safe APIs. Most application code never needs raw pointers. Interop design must account for ownership, calling conventions, string encoding, structure layout, pinning, and error propagation.
