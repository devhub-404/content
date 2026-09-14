# Structs y Tuple Structs

Una struct agrupa fields relacionados en un tipo nombrado. Las named-field structs sirven para records; las tuple structs son útiles para newtypes o pequeños agrupamientos posicionales; las unit structs no almacenan fields.

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

La struct update syntax puede mover fields non-Copy desde otro valor, así que observa el ownership. Prefiere constructors/validation cuando no toda combinación de fields públicos sea válida.
