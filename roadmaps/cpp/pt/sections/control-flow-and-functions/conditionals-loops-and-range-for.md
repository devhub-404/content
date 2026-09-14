# Condicionais, Loops e Range-for

C++ possui `if`, `switch`, `for`, `while`, `do` e range-based `for`. C++17+ também permite initializer em `if` e `switch`, útil para manter temporários no scope da decisão.

```cpp
for (const auto &item : items) {
    if (!item.active) {
        continue;
    }
    process(item);
}
```

Use range-for quando precisa dos elementos, não do índice, mas escolha a variável: `auto item` pode copiar, enquanto `const auto&` faz borrow. Use índices quando a posição em si importa ou quando precisa coordenar várias sequências.
