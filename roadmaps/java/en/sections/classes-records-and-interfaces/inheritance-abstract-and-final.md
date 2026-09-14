# Inheritance, Abstract Classes, and `final`

Java classes support single inheritance, while abstract classes can share implementation and require subclasses to implement selected methods. Dynamic dispatch chooses the overridden instance method at runtime. `final` can prevent extension or overriding.

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

Use inheritance for genuine substitutability, not merely because two classes share code. Composition and interfaces are often simpler when one object uses another capability rather than being a specialized version of it.
