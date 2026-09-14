# Procedural Macros y Derives

Las procedural macros se ejecutan en compile time y transforman token streams. Sustentan custom derives, attribute-like y function-like macros usadas en serialización, web, databases y async.

```rust
#[derive(Debug, Clone)]
struct User {
    id: u64,
    name: String,
}
```

Una proc macro es un crate separado con mucho poder y puede ocultar comportamiento generado. Prefiere APIs transparentes/docs, inspecciona expansions al depurar y evita macro magic cuando un trait/función normal sea más claro.
