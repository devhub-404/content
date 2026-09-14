# Ranges and Views

The ranges library lets algorithms work with range objects directly and adds composable views. Views are usually lightweight lazy adaptors that describe iteration rather than eagerly constructing a new container.

```cpp
auto even_squares =
    values
    | std::views::filter([](int x) { return x % 2 == 0; })
    | std::views::transform([](int x) { return x * x; });

for (int value : even_squares) {
    std::cout << value << '
';
}
```

Lazy views can reference the underlying source, so lifetime and mutation still matter. A pipeline is useful when each stage communicates a clear transformation; if debugging or complexity becomes opaque, materializing an intermediate container can be the clearer engineering choice.
