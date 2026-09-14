# Condicionales, Loops y Range-for

C++ tiene `if`, `switch`, `for`, `while`, `do` y range-based `for`. Desde C++17 también se permiten initializers en `if` y `switch`, útiles para mantener temporales dentro del scope de la decisión.

```cpp
for (const auto &item : items) {
    if (!item.active) {
        continue;
    }
    process(item);
}
```

Usa range-for cuando necesitas elementos y no índices, pero elige bien la variable: `auto item` puede copiar, mientras `const auto&` hace borrow. Usa índices cuando la posición importa o necesitas coordinar varias secuencias.
