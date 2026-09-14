# `std::unique_ptr`

`std::unique_ptr<T>` models exclusive ownership of a dynamically allocated object or other resource through a configurable deleter. It is move-only, so transferring it makes the ownership change explicit in the type system.

```cpp
auto user = std::make_unique<user_record>();
user->name = "Mina";

auto transferred = std::move(user);
```

Prefer `std::make_unique` for ordinary heap construction and pass `unique_ptr` by value when a function takes ownership. Borrow through `T&` or `T*` when the function does not own the object. Do not use a smart pointer merely as a fancy nullable reference when no ownership is involved.
