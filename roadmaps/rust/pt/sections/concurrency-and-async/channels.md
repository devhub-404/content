# Channels

Message passing move/copia valores entre componentes por channels. `mpsc` padrão possui múltiplos producers e um consumer; clones de sender representam producers adicionais.

```rust
use std::sync::mpsc;
use std::thread;

let (tx, rx) = mpsc::channel();

thread::spawn(move || {
    tx.send(String::from("done")).unwrap();
});

println!("{}", rx.recv().unwrap());
```

Fechamento do channel ocorre quando todos senders são dropped e serve como lifecycle signal. Evite protocols onde os lados podem esperar para sempre. Runtimes async do ecossistema oferecem outros channels com semânticas diferentes.
