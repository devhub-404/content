# `let`, `mut` e Shadowing

Bindings são imutáveis por default. Use `mut` quando o valor será alterado por aquele binding. Shadowing com novo `let` cria outro binding e pode mudar o tipo, ao contrário de mutation, que mantém binding e tipo.

```rust
let count = 10;
let mut total = 0;

total += count;

let count = count.to_string();
```

Imutabilidade default torna mudanças de estado visíveis e ajuda o borrow checker. Use mutation quando pertence ao algoritmo e shadowing para transformações em etapas onde o binding anterior é conceitualmente substituído.
