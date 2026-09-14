# Templates de Función

Un function template describe una familia de funciones parametrizada por tipos, valores u otros templates. En la llamada, template argument deduction determina una specialization. Es generic programming de compile time, no dispatch dinámico.

```cpp
template <typename T>
T max_value(T a, T b) {
    return b < a ? a : b;
}

auto best = max_value(10, 20);
```

Los templates funcionan mejor cuando la implementación sirve realmente a varios tipos con una capacidad compartida. Si las operaciones válidas forman parte del contrato público, concepts hacen esos requisitos mucho más claros que errores de sustitución profundos.
