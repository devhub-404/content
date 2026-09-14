# Tuples y Deconstruction

Los value tuples agrupan pocos valores con nombres opcionales y la deconstruction asigna componentes a variables separadas. Classes, records y custom types también pueden participar mediante `Deconstruct`.

```csharp
static (int Min, int Max) Bounds(IEnumerable<int> values)
{
    return (values.Min(), values.Max());
}

var (min, max) = Bounds([3, 8, 2]);
```

Los tuples funcionan bien para resultados locales pequeños. Cuando el shape cruza un boundary público, crece muchos campos o necesita comportamiento/validación, un record o struct con nombre comunica mejor.
