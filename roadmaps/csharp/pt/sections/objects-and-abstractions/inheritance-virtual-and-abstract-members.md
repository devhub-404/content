# Herança, Members Virtual e Abstract

Classes suportam herança simples de classes e dispatch polimórfico por `virtual`, `abstract` e `override`. Abstract class pode compartilhar implementação/estado e exigir members de subclasses. `sealed` impede herança ou override adicional.

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

Use herança para substituibilidade real, não apenas reuso. Hierarquias profundas tornam estado e lifecycle difíceis; composição e interfaces costumam ser melhores quando um tipo apenas usa outra capacidade.
