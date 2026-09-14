# Channels

Los channels son primitivas tipadas de comunicación y sincronización. Send transmite un valor, receive lo obtiene, un channel unbuffered sincroniza sender/receiver y uno buffered permite cierta cola.

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

Close indica que no habrá nuevos sends; los receivers pueden drenar valores existentes. El lado que posee el lifecycle de producción suele cerrar el channel. Enviar a un channel cerrado o cerrarlo dos veces produce panic.
