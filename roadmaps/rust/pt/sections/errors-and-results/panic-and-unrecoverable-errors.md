# `panic!` e Erros Irrecuperáveis

`panic!` representa falha irrecuperável no caminho atual. Panic pode unwind stack ou abortar conforme configuração, e unwinding executa destructors dos valores vivos.

```rust
fn positive(value: i32) -> i32 {
    assert!(value > 0, "value must be positive");
    value
}
```

Use panic para invariantes internas violadas, estados impossíveis ou testes, não para input inválido, file missing ou network failures recuperáveis. APIs não devem surpreender callers com panics rotineiros quando `Result` serviria.
