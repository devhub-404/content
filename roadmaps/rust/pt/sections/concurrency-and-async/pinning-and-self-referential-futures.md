# Pinning e Futures Self-referential

`Pin<P>` expressa que pointee não pode ser movido de forma que quebre invariantes. State machines async e estruturas self-referential dependem disso porque references internas podem invalidar se o valor mover após poll.

```rust
use std::pin::Pin;
use std::future::Future;

fn poll_later(
    future: Pin<&mut dyn Future<Output = ()>>
) {
    // an executor may poll this pinned future
}
```

Maior parte do código async não manipula `Pin` manualmente; executors e async machinery escondem detalhes. Aprenda conceito para entender APIs avançadas, mas não introduza pinning sem necessidade real.
