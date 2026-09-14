# Structs e Tuple Structs

Struct agrupa fields relacionados em tipo nomeado. Named-field structs servem a records; tuple structs são úteis para newtypes ou pequenos agrupamentos posicionais; unit structs não armazenam fields.

```rust
struct User {
    id: u64,
    name: String,
}

struct UserId(u64);

let user = User {
    id: 42,
    name: String::from("Mina"),
};
```

Struct update syntax pode mover fields non-Copy de outro valor, então observe ownership. Prefira constructors/validation quando nem toda combinação de fields públicos é válida.
