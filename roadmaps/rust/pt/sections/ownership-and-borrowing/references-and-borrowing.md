# References e Borrowing

Reference faz borrow de um valor sem assumir ownership. `&T` fornece acesso read-only e o owner continua responsável pelo lifetime. Borrowing permite usar dados sem moves/copies desnecessários.

```rust
fn length(text: &String) -> usize {
    text.len()
}

let name = String::from("Mina");
let size = length(&name);

println!("{name} {size}");
```

Borrow checker garante que references não sobrevivam aos dados e aplica regras de aliasing. Prefira parâmetros borrowed como `&str` ou `&[T]` quando função só precisa observar e não assumir ownership.
