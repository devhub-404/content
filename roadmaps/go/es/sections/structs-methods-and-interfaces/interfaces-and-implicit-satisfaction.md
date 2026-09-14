# Interfaces y Satisfacción Implícita

Una interface describe un conjunto de methods y un tipo concreto la satisface implícitamente al tener el method set requerido. No existe `implements`, manteniendo la dependencia orientada al comportamiento que realmente necesita el consumidor.

```go
type Writer interface {
    Write([]byte) (int, error)
}

func save(w Writer, data []byte) error {
    _, err := w.Write(data)
    return err
}
```

Prefiere interfaces pequeñas definidas cerca del consumer. Una función que solo necesita `Write` no debe aceptar una interface enorme. Los method sets de `T` y `*T` siguen importando según los receivers.
