# Channels

El message passing mueve/copia valores entre componentes mediante channels. El `mpsc` estándar tiene múltiples producers y un consumer; clones del sender representan producers adicionales.

```rust
use std::sync::mpsc;
use std::thread;

let (tx, rx) = mpsc::channel();

thread::spawn(move || {
    tx.send(String::from("done")).unwrap();
});

println!("{}", rx.recv().unwrap());
```

El cierre del channel ocurre cuando todos los senders son dropped y sirve como lifecycle signal. Evita protocols donde ambos lados puedan esperar para siempre. Los runtimes async del ecosistema ofrecen otros channels con semánticas distintas.
