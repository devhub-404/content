# Object Slicing and Polymorphic Ownership

Copying a derived object into a base object by value slices away the derived part. Runtime polymorphism therefore usually travels through references or pointers, not base objects copied by value.

```cpp
std::unique_ptr<shape> make_shape() {
    return std::make_unique<circle>(2.0);
}
```

For owning polymorphic objects, `std::unique_ptr<Base>` is a common default when there is one owner, while `std::shared_ptr` is appropriate only when lifetime is genuinely shared. A virtual destructor and a clear ownership model are both required; polymorphism alone does not solve resource management.
