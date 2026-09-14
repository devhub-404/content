# Pinning y Futures Self-referential

`Pin<P>` expresa que el pointee no puede moverse de forma que rompa invariantes. Las state machines async y estructuras self-referential dependen de ello porque references internas pueden invalidarse si el valor se mueve tras ser polled.

```rust
use std::pin::Pin;
use std::future::Future;

fn poll_later(
    future: Pin<&mut dyn Future<Output = ()>>
) {
    // an executor may poll this pinned future
}
```

La mayor parte del código async no manipula `Pin` manualmente; executors y async machinery ocultan los detalles. Aprende el concepto para entender APIs avanzadas, pero no introduzcas pinning sin una necesidad real.
