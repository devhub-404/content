# Structs e Value Types

Structs são value types. Assignment, passagem de parâmetros e armazenamento em collections normalmente copiam a representação salvo quando há modifier de referência. Valores pequenos e imutáveis como coordenadas, IDs e wrappers numéricos são bons candidatos.

```csharp
public readonly struct Point
{
    public double X { get; }
    public double Y { get; }

    public Point(double x, double y) =>
        (X, Y) = (x, y);
}
```

Structs grandes e mutáveis são difíceis porque cópias podem ficar escondidas e mutation pode atingir apenas uma cópia. Prefira readonly structs para value objects e classes quando identidade compartilhada ou estado mutável são centrais.
