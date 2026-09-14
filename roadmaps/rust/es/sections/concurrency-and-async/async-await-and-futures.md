# `async`, `await` y `Future`

Una `async fn` retorna un future: un valor que representa trabajo que progresa cuando un executor lo poll. `.await` suspende la task hasta que el future esté ready, permitiendo al executor ejecutar otro trabajo sin bloquear el thread.

```rust
async fn load() -> Result<String, Error> {
    let first = fetch_part_one().await?;
    let second = fetch_part_two().await?;
    Ok(format!("{first}{second}"))
}
```

La std define `Future`, pero no un runtime async universal ni reactor de red; las aplicaciones eligen un runtime del ecosistema. Awaits consecutivos serializan trabajo; futures independientes requieren composición concurrente explícita.
