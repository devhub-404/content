# `async`, `await`, and `Future`

An `async fn` returns a future: a value representing work that can make progress when polled by an executor. `.await` suspends the current async task until the awaited future is ready, allowing the executor to run other work rather than blocking the thread.

```rust
async fn load() -> Result<String, Error> {
    let first = fetch_part_one().await?;
    let second = fetch_part_two().await?;
    Ok(format!("{first}{second}"))
}
```

The standard library defines `Future` but does not provide a universal async runtime or network reactor, so applications usually choose an ecosystem runtime. Consecutive awaits serialize dependent work; independent futures may need explicit concurrent composition supplied by the runtime or utilities.
