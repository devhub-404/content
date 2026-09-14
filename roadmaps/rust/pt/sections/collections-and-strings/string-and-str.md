# `String` e `str`

`String` possui buffer UTF-8 growable e `str` é string slice unsized normalmente usada como `&str`. Nenhum suporta indexação inteira arbitrária porque um offset pode cair dentro de code point multibyte.

```rust
let mut owned = String::from("Olá");
owned.push_str(", Rust");

let borrowed: &str = &owned;
println!("{borrowed}");
```

Escolha se domínio trabalha com bytes, Unicode scalar values (`chars()`) ou grapheme clusters. Prefira `&str` para texto borrowed e `String` quando ownership/mutation são necessários.
