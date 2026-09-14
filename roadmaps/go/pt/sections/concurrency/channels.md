# Channels

Channels são primitives tipadas de comunicação e sincronização. Send transmite valor, receive obtém, channel unbuffered sincroniza sender/receiver e buffered permite certa quantidade em fila.

```go
jobs := make(chan int)

go func() {
    for job := range jobs {
        process(job)
    }
}()

jobs <- 42
close(jobs)
```

Close sinaliza que não haverá novos sends; receivers ainda drenam valores existentes. O lado que possui lifecycle de produção normalmente fecha o channel. Send em closed channel e close duplo causam panic.
