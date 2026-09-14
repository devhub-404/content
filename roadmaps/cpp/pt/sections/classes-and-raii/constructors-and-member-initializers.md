# Constructors e Inicialização de Membros

Constructors estabelecem a invariante inicial do objeto. Data members são inicializados na ordem de declaração, não na ordem textual da initializer list. Prefira inicialização direta a default construction seguida de assignment no corpo.

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

Marque constructors de um argumento como `explicit` quando conversão implícita seria surpreendente. Default member initializers reduzem repetição. Se construção pode falhar de forma recuperável, uma factory com resultado de erro pode ser melhor que objeto meio-válido.
