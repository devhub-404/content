# `IEnumerable<T>` and `yield`

`IEnumerable<T>` is the central synchronous sequence abstraction. An iterator method using `yield return` lets the compiler generate an enumerator state machine so values can be produced lazily as the consumer asks for them.

```csharp
static IEnumerable<int> EvenNumbers(int max)
{
    for (int i = 0; i <= max; i += 2)
    {
        yield return i;
    }
}
```

Laziness means the method body may not run when the sequence is created; it runs during enumeration. Be careful with exceptions, expensive work, database contexts, and mutable captured state whose lifetime extends until enumeration finishes.
