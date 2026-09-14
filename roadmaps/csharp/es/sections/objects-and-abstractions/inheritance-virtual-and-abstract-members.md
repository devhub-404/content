# Herencia, Members Virtual y Abstract

Las classes soportan herencia simple de clases y dispatch polimórfico mediante `virtual`, `abstract` y `override`. Una abstract class puede compartir implementación/estado y exigir members de subclases. `sealed` impide herencia u override adicional.

```csharp
public abstract class Shape
{
    public abstract double Area { get; }
}

public sealed class Circle(double radius) : Shape
{
    public override double Area => Math.PI * radius * radius;
}
```

Usa herencia para sustitución real, no solo reutilización. Jerarquías profundas hacen estado y lifecycle más difíciles; composición e interfaces suelen ser mejores cuando un tipo solo usa otra capacidad.
