# `Box<T>`

`Box<T>` posee un valor asignado en el heap y tiene representación pointer-sized. Es común en tipos recursivos, valores que deben moverse por pointer y trait objects owning.

```rust
enum List {
    Cons(i32, Box<List>),
    Nil,
}
```

No uses `Box` solo porque un objeto parezca grande sin medir. Úsalo cuando indirection o heap ownership estable forme parte del requisito estructural.
