# Herança e Funções Virtuais

Herança public modela relação is-a onde objeto derivado pode ser usado pela interface base. Virtual functions permitem dispatch de runtime por reference/pointer da base, e `override` verifica que o membro realmente sobrescreve função virtual.

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

Base polimórfica destruída por base pointer normalmente precisa de virtual destructor. Prefira herança para substituibilidade comportamental estável, não só reuso de implementação. Composição costuma ser mais simples quando um tipo apenas contém ou delega a outro.
