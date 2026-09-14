# `async`, `await` e `Future`

`async fn` retorna future: valor representando trabalho que progride quando polled por executor. `.await` suspende a task até o future ficar ready, permitindo ao executor rodar outras tasks sem bloquear thread.

```rust
async fn load() -> Result<String, Error> {
    let first = fetch_part_one().await?;
    let second = fetch_part_two().await?;
    Ok(format!("{first}{second}"))
}
```

Std define `Future`, mas não runtime async universal/network reactor; aplicações escolhem runtime do ecossistema. Awaits consecutivos serializam trabalho; futures independentes exigem composição concorrente explícita.
