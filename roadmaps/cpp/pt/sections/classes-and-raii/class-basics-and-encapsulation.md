# Fundamentos de Classes e Encapsulamento

Uma class define tipo com data members, member functions, access control, constructors e comportamentos especiais. `class` defaulta acesso private e `struct` public; fora isso ambos podem definir os mesmos membros.

```cpp
class account {
public:
    explicit account(std::string owner)
        : owner_(std::move(owner)) {}

    double balance() const {
        return balance_;
    }

private:
    std::string owner_;
    double balance_ = 0.0;
};
```

Encapsulamento é útil quando o tipo mantém invariantes. Mantenha estado private quando callers não devem criar combinações inválidas e exponha operações que preservam o contrato. Evite getters/setters mecânicos que apenas recriam um data struct público.
