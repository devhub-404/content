# `Deref` e `Drop`

`Drop` executa cleanup determinístico ao sair de scope, tornando RAII central. `Deref`/`DerefMut` permitem que smart-pointer-like types exponham target e participem de deref coercions.

```rust
struct Guard {
    name: String,
}

impl Drop for Guard {
    fn drop(&mut self) {
        println!("releasing {}", self.name);
    }
}
```

Implemente `Deref` apenas quando tipo realmente se comporta como smart pointer. `Drop` deve liberar recursos confiavelmente e não deve depender de process termination. Evite cycles que impedem owners de serem dropped.
