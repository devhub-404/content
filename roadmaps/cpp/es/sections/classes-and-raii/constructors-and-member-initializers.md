# Constructors e Inicialización de Miembros

Los constructors establecen la invariante inicial del objeto. Los data members se inicializan en orden de declaración, no en el orden textual de la initializer list. Prefiere inicialización directa frente a construir por defecto y asignar después.

```cpp
class point {
public:
    point(double x, double y)
        : x_(x), y_(y) {}

private:
    double x_;
    double y_;
};
```

Marca constructors de un argumento como `explicit` cuando una conversión implícita sería sorprendente. Los default member initializers reducen repetición. Si la construcción puede fallar de forma recuperable, una factory con resultado de error puede ser mejor que un objeto medio válido.
