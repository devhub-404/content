# Interfaces e Satisfação Implícita

Interface descreve conjunto de methods e um tipo concreto a satisfaz implicitamente ao possuir method set exigido. Não existe `implements`, mantendo dependência orientada ao comportamento de que o consumidor realmente precisa.

```go
type Writer interface {
    Write([]byte) (int, error)
}

func save(w Writer, data []byte) error {
    _, err := w.Write(data)
    return err
}
```

Prefira interfaces pequenas definidas perto do consumer. Uma função que só precisa de `Write` não deve aceitar interface enorme. Method sets de `T` e `*T` continuam importando conforme os receivers.
