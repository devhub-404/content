# Methods, Parameters, and Return Values

Method signatures specify parameter and return types, overloads can share a name with distinguishable signatures, and optional/named arguments improve selected APIs. Parameter modifiers such as `ref`, `out`, `in`, and `params` change how arguments are passed or grouped.

```csharp
static bool TryDivide(
    double a,
    double b,
    out double result)
{
    if (b == 0)
    {
        result = default;
        return false;
    }

    result = a / b;
    return true;
}
```

Prefer ordinary value parameters and return values until a modifier expresses a real need. `out` is useful for try-pattern APIs, while `ref` exposes aliasing and should not be used merely to avoid copying small values.
