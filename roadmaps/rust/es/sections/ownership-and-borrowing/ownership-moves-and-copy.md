# Ownership, Moves y `Copy`

Todo valor Rust tiene un owner y, cuando el ownership se mueve a otro binding o función, el binding anterior ya no puede usar ese valor salvo si el tipo implementa `Copy`. Esto evita que dos owners normales liberen el mismo recurso.

```rust
let first = String::from("hello");
let second = first;

// println!("{first}"); // moved
println!("{second}");

let a = 10;
let b = a; // i32 implements Copy
println!("{a} {b}");
```

Tipos pequeños como enteros suelen implementar `Copy`; tipos owning como `String` no. Un move suele transferir fields de forma barata, no hacer deep copy. Si necesitas duplicar datos owning, usa `clone()` deliberadamente.
