# Channels

Message passing moves or copies values between concurrent components through channels. The standard `mpsc` channel has multiple producers and one consumer, with sender clones representing additional producers.

```rust
use std::sync::mpsc;
use std::thread;

let (tx, rx) = mpsc::channel();

thread::spawn(move || {
    tx.send(String::from("done")).unwrap();
});

println!("{}", rx.recv().unwrap());
```

Channel closure becomes a useful lifecycle signal when all senders are dropped. Avoid designing protocols that can deadlock because both sides wait forever. For advanced async/multi-consumer patterns, ecosystem runtimes provide additional channel implementations with different semantics.
