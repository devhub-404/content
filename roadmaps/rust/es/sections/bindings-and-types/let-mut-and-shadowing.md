# `let`, `mut` y Shadowing

Los bindings son inmutables por defecto. Usa `mut` cuando el valor vaya a cambiar a través de ese binding. Shadowing con un nuevo `let` crea otro binding y puede cambiar el tipo, a diferencia de mutation, que conserva binding y tipo.

```rust
let count = 10;
let mut total = 0;

total += count;

let count = count.to_string();
```

La inmutabilidad por defecto hace visibles los cambios de estado y ayuda al borrow checker. Usa mutation cuando forme parte del algoritmo y shadowing para transformaciones por etapas donde el binding anterior queda conceptualmente reemplazado.
