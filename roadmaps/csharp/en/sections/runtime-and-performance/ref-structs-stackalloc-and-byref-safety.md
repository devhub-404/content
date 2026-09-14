# `ref struct`, `stackalloc`, and By-ref Safety

By-ref features let C# work with stack memory and references without copying values. `ref struct` types such as `Span<T>` are restricted so references to stack data cannot escape into invalid lifetimes, and `stackalloc` creates storage whose lifetime is the current stack frame.

```csharp
Span<int> values = stackalloc int[4];
values[0] = 10;

ref int first = ref values[0];
first = 20;
```

Use these features only when memory layout and allocation cost matter. The safety rules are deliberately strict; fighting them often means the design is trying to let short-lived memory escape farther than it should.
