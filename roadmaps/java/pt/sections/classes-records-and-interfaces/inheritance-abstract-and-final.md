# Herança, Abstract Classes e `final`

Classes Java suportam herança simples e abstract classes podem compartilhar implementação e exigir methods de subclasses. Dispatch dinâmico escolhe override em runtime. `final` pode impedir extension ou overriding.

```java
abstract class Shape {
    abstract double area();
}

final class Circle extends Shape {
    private final double radius;
    Circle(double radius) { this.radius = radius; }
    @Override double area() { return Math.PI * radius * radius; }
}
```

Use herança para substituibilidade real, não só código compartilhado. Composição e interfaces são melhores quando um objeto apenas usa outra capacidade.
