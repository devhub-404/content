# Futures e `std::async`

`std::future` representa resultado disponível depois e pode receber valores de promises, packaged tasks ou `std::async`. `get()` espera e retorna resultado ou relança a exception armazenada.

```cpp
auto future = std::async(
    std::launch::async,
    [] { return expensive_work(); }
);

auto result = future.get();
```

`std::async` possui launch policies que podem surpreender se implícitas, e futures são building block relativamente baixo nível. Use quando seu modelo de ownership e espera se encaixar claramente no problema.
