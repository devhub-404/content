# `std::shared_ptr` e `std::weak_ptr`

`std::shared_ptr` usa ownership compartilhado com reference count; o recurso permanece vivo até o último owner ser destruído/resetado. `std::weak_ptr` observa o mesmo control block sem manter ownership e pode ser temporariamente locked.

```cpp
auto resource = std::make_shared<resource_type>();
std::weak_ptr<resource_type> observer = resource;

if (auto locked = observer.lock()) {
    use(*locked);
}
```

Use shared ownership apenas quando vários componentes realmente co-possuem o lifetime. Ciclos de `shared_ptr` impedem liberação e weak pointers quebram arestas não-owning. Reference counting também tem custo comparado a um owner claro.
