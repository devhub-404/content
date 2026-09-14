# Tipos Escalares y Compuestos

Los tipos escalares incluyen enteros signed/unsigned con anchuras explícitas, `isize`/`usize`, floating point, `bool` y `char` Unicode. Los tipos compuestos built-in incluyen tuples y arrays fijos.

```rust
let age: u32 = 42;
let ratio: f64 = 0.75;
let ready: bool = true;
let letter: char = '🦀';

let pair: (i32, &str) = (7, "days");
let values: [i32; 3] = [1, 2, 3];
```

Elige anchuras según contrato y rango. `usize` es natural para índices/sizes. La política de overflow debe ser explícita cuando el dominio requiera un comportamiento concreto, usando operaciones checked, wrapping, saturating u overflowing.
