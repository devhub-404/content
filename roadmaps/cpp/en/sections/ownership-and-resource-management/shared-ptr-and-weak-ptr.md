# `std::shared_ptr` and `std::weak_ptr`

`std::shared_ptr` uses shared reference-counted ownership: the managed resource remains alive until the last owning shared pointer is destroyed or reset. `std::weak_ptr` observes the same control block without contributing to ownership and can be locked temporarily.

```cpp
auto resource = std::make_shared<resource_type>();
std::weak_ptr<resource_type> observer = resource;

if (auto locked = observer.lock()) {
    use(*locked);
}
```

Use shared ownership only when multiple components genuinely co-own the lifetime. Cycles of `shared_ptr` prevent reclamation; weak pointers can break non-owning edges. Reference counting also has runtime and synchronization cost compared with a single clear owner.
