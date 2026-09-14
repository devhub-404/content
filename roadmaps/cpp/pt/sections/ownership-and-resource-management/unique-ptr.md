# `std::unique_ptr`

`std::unique_ptr<T>` modela ownership exclusivo de objeto alocado dinamicamente ou outro recurso via deleter configurável. É move-only, então transferir deixa a mudança de ownership explícita.

```cpp
auto user = std::make_unique<user_record>();
user->name = "Mina";

auto transferred = std::move(user);
```

Prefira `std::make_unique` para alocação comum e passe `unique_ptr` por valor quando a função assume ownership. Faça borrow com `T&` ou `T*` quando não assume. Não use smart pointer apenas como nullable reference sem ownership.
