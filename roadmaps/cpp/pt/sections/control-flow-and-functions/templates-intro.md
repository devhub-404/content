# Templates de Função

Function template descreve uma família de funções parametrizada por tipos, valores ou outros templates. Na chamada, template argument deduction determina uma specialization. É generic programming de compile time, não dispatch dinâmico.

```cpp
template <typename T>
T max_value(T a, T b) {
    return b < a ? a : b;
}

auto best = max_value(10, 20);
```

Templates funcionam melhor quando a implementação realmente serve a vários tipos com uma capacidade comum. Se as operações válidas fazem parte do contrato público, concepts tornam esses requisitos muito mais claros que falhas de substituição profundas.
