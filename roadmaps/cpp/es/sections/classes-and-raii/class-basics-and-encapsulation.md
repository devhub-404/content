# Fundamentos de Classes y Encapsulación

Una class define un tipo con data members, member functions, access control, constructors y comportamientos especiales. `class` usa acceso private por defecto y `struct` public; por lo demás ambos pueden definir los mismos miembros.

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

La encapsulación es útil cuando el tipo mantiene invariantes. Mantén el estado private si callers no deben crear combinaciones inválidas y expón operaciones que preserven el contrato. Evita getters/setters mecánicos que solo recrean un data struct público.
