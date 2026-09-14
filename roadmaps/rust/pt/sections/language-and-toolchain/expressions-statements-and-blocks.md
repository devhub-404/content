# Expressões, Statements e Blocos

Rust é expression-oriented. Literals, chamadas, `if`, `match` e blocos podem produzir valores. A expressão final de um bloco sem semicolon vira seu resultado; adicionar semicolon transforma-a em statement com resultado `()`.

```rust
fn square(x: i32) -> i32 {
    let result = {
        let y = x * x;
        y
    };

    result
}
```

Isso explica o idiom de retornar a expressão final sem `return`. Use control flow orientado a expressões quando deixa fluxo de dados claro, sem comprimir vários side effects em uma expressão difícil de ler.
