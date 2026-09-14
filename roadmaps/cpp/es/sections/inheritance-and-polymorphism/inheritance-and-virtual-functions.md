# Herencia y Funciones Virtuales

La herencia public modela una relación is-a donde el objeto derivado puede usarse mediante la interfaz base. Las virtual functions permiten dispatch de runtime por reference/pointer de base y `override` verifica que el miembro realmente sobrescribe una función virtual.

```cpp
class shape {
public:
    virtual ~shape() = default;
    virtual double area() const = 0;
};

class circle : public shape {
public:
    explicit circle(double r) : r_(r) {}
    double area() const override { return 3.14159 * r_ * r_; }

private:
    double r_;
};
```

Una base polimórfica que se destruye mediante base pointer suele necesitar virtual destructor. Prefiere herencia para sustitución comportamental estable, no solo para reutilizar implementación. La composición suele ser más simple cuando un tipo solo contiene o delega en otro.
