# Pattern Matching com `match`

`match` compara valor com patterns e exige tratamento exaustivo. Patterns podem destructure enums, tuples, structs, references, ranges, literals e dados aninhados; guards adicionam condição booleana.

```rust
match status {
    Status::Ready => start(),
    Status::Failed(code) if code >= 500 => retry(),
    Status::Failed(code) => log_error(code),
    Status::Pending => wait(),
}
```

Exaustividade transforma mudanças de estado em trabalho de compile time: adicionar variant revela matches a atualizar. Prefira enum variants a sentinels e booleans soltos quando o state space é conhecido.
