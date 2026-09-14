# Arrays, Lists y Collection Expressions

Los arrays tienen length fijo y acceso indexado eficiente, mientras `List<T>` es la colección growable estándar. Las collection expressions ofrecen sintaxis compacta para arrays, lists, spans y destinos compatibles.

```csharp
int[] fixedValues = [1, 2, 3];
List<int> values = [1, 2, 3];
values.Add(4);

ReadOnlySpan<int> span = [10, 20, 30];
```

Elige array cuando el almacenamiento contiguo de tamaño fijo sea el contrato y list para secuencias dinámicas normales. Expón `IReadOnlyList<T>` o `IEnumerable<T>` cuando los callers no necesiten mutation.
