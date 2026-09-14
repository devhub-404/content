# `if`, `loop`, `while` y `for`

`if` es una expresión y los branches deben producir tipos compatibles cuando se usa su valor. `loop` repite indefinidamente y puede producir un valor mediante `break expression`. `while` maneja repetición condicional y `for` consume un iterator.

```rust
let label = if ready { "ready" } else { "waiting" };

for value in values {
    println!("{value}");
}

let result = loop {
    if done() {
        break 42;
    }
};
```

Prefiere `for` frente a indexación manual cuando solo necesitas elementos. Los labels pueden dirigirse a loops exteriores, pero un nesting profundo suele mejorar al extraer una función con early return.
