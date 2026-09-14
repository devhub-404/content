# Local Functions and Expression-bodied Members

Local functions let a method define a helper whose scope is limited to that method, and they can capture surrounding state unless declared `static`. Expression-bodied syntax uses `=>` for members whose implementation is naturally one expression.

```csharp
static int SumPositive(IEnumerable<int> values)
{
    return values.Sum(IsPositive);

    static int IsPositive(int value) =>
        value > 0 ? value : 0;
}
```

Use these forms to improve locality, not to hide large functions inside other large functions. A static local function is especially useful when you want the compiler to guarantee that the helper does not accidentally capture outer variables.
