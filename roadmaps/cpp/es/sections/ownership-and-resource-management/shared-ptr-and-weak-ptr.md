# `std::shared_ptr` y `std::weak_ptr`

`std::shared_ptr` usa ownership compartido con reference counting; el recurso vive hasta que el último owner se destruye o resetea. `std::weak_ptr` observa el mismo control block sin mantener ownership y puede bloquearse temporalmente.

```cpp
auto resource = std::make_shared<resource_type>();
std::weak_ptr<resource_type> observer = resource;

if (auto locked = observer.lock()) {
    use(*locked);
}
```

Usa shared ownership solo cuando varios componentes realmente co-poseen el lifetime. Los ciclos de `shared_ptr` impiden liberar recursos y weak pointers rompen aristas no-owning. El reference counting también tiene coste frente a un único owner claro.
