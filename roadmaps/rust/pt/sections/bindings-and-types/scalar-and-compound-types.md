# Tipos Escalares e Compostos

Tipos escalares incluem inteiros signed/unsigned com larguras explícitas, `isize`/`usize`, floating point, `bool` e `char` Unicode. Tipos compostos built-in incluem tuples e arrays fixos.

```rust
let age: u32 = 42;
let ratio: f64 = 0.75;
let ready: bool = true;
let letter: char = '🦀';

let pair: (i32, &str) = (7, "days");
let values: [i32; 3] = [1, 2, 3];
```

Escolha larguras pelo contrato e range. `usize` é natural para índices/sizes. Política de overflow deve ser explícita quando o domínio exige comportamento específico, usando operações checked, wrapping, saturating ou overflowing.
