# Ownership, Moves e `Copy`

Todo valor Rust possui owner, e quando ownership move para outro binding/função o binding antigo não pode mais usar aquele valor salvo se o tipo implementa `Copy`. Isso impede dois owners comuns de liberarem o mesmo recurso.

```rust
let first = String::from("hello");
let second = first;

// println!("{first}"); // moved
println!("{second}");

let a = 10;
let b = a; // i32 implements Copy
println!("{a} {b}");
```

Tipos pequenos como inteiros normalmente implementam `Copy`; tipos owning como `String` não. Move costuma transferir fields de forma barata, não deep copy. Quando precisa duplicar dados owning, use `clone()` deliberadamente.
