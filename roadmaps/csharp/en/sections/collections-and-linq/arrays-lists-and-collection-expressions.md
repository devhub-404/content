# Arrays, Lists, and Collection Expressions

Arrays have fixed length and efficient indexed storage, while `List<T>` is the standard growable indexed collection. Collection expressions provide compact syntax that can target arrays, lists, spans, and other collection-builder-compatible destinations.

```csharp
int[] fixedValues = [1, 2, 3];
List<int> values = [1, 2, 3];
values.Add(4);

ReadOnlySpan<int> span = [10, 20, 30];
```

Choose arrays when fixed-size contiguous storage is the real contract and lists for ordinary dynamic sequences. Expose `IReadOnlyList<T>` or `IEnumerable<T>` when callers do not need mutation-specific capabilities.
