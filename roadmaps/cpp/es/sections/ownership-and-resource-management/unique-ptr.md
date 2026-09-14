# `std::unique_ptr`

`std::unique_ptr<T>` modela ownership exclusivo de un objeto asignado dinámicamente u otro recurso mediante un deleter configurable. Es move-only, por lo que transferirlo hace explícito el cambio de ownership.

```cpp
auto user = std::make_unique<user_record>();
user->name = "Mina";

auto transferred = std::move(user);
```

Prefiere `std::make_unique` para construcción normal y pasa `unique_ptr` por valor cuando una función toma ownership. Haz borrow con `T&` o `T*` cuando no lo toma. No uses smart pointers como simples nullable references si no hay ownership.
