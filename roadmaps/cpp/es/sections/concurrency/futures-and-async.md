# Futures y `std::async`

`std::future` representa un resultado disponible más tarde y puede recibir valores de promises, packaged tasks o `std::async`. `get()` espera y devuelve el resultado o relanza la exception almacenada.

```cpp
auto future = std::async(
    std::launch::async,
    [] { return expensive_work(); }
);

auto result = future.get();
```

`std::async` tiene launch policies que pueden sorprender si quedan implícitas y futures son un building block relativamente low-level. Úsalos cuando su modelo de ownership y espera encaje claramente en el problema.
