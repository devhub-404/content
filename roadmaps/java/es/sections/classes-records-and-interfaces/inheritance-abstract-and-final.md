# Herencia, Abstract Classes y `final`

Las classes Java soportan herencia simple y las abstract classes pueden compartir implementación y exigir methods de subclases. El dispatch dinámico elige el override en runtime. `final` puede impedir extension u overriding.

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

Usa herencia para sustitución real, no solo código compartido. Composición e interfaces son mejores cuando un objeto solo usa otra capacidad.
