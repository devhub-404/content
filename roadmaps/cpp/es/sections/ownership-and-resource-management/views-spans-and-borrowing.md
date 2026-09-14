# `std::span`, `std::string_view` y Views Borrowed

`std::span` es una view no-owning de una secuencia contigua y `std::string_view` de datos de caracteres. Encapsulan pointer-plus-length sin asignar ni poseer el almacenamiento subyacente.

```cpp
void print_values(std::span<const int> values) {
    for (int value : values) {
        std::cout << value << '
';
    }
}

void log(std::string_view message);
```

La seguridad depende del lifetime: los datos de origen deben vivir más que la view. Nunca devuelvas una view hacia un temporal o local que será destruido. Son excelentes tipos de borrow en APIs cuando el ownership permanece en otro lugar.
