# Structs y Value Types

Las structs son value types. Assignment, paso de parámetros y almacenamiento en collections normalmente copian la representación salvo que intervenga un modifier de referencia. Valores pequeños e inmutables como coordenadas, IDs y wrappers numéricos son buenos candidatos.

```csharp
public readonly struct Point
{
    public double X { get; }
    public double Y { get; }

    public Point(double x, double y) =>
        (X, Y) = (x, y);
}
```

Las structs grandes y mutables son difíciles porque las copias pueden quedar ocultas y la mutation afectar solo a una copia. Prefiere readonly structs para value objects y classes cuando identidad compartida o estado mutable sean centrales.
