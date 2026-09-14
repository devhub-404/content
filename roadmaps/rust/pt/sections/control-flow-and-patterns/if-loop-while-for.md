# `if`, `loop`, `while` e `for`

`if` é expressão e os branches precisam produzir tipos compatíveis quando seu valor é usado. `loop` repete indefinidamente e pode produzir valor com `break expression`. `while` trata repetição condicional e `for` consome iterator.

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

Prefira `for` a indexação manual quando precisa apenas dos elementos. Labels podem atingir loops externos, mas nesting profundo frequentemente melhora ao extrair função com early return.
