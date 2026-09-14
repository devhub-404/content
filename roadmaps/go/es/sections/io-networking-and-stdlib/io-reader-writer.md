# `io.Reader` y `io.Writer`

`io.Reader` y `io.Writer` son interfaces pequeñas que conectan gran parte del ecosistema. Archivos, buffers, network connections, compressors, hashers y HTTP bodies pueden componerse porque comparten esos contratos.

```go
func copyToFile(
    dst io.Writer,
    src io.Reader,
) error {
    _, err := io.Copy(dst, src)
    return err
}
```

Diseña streaming APIs sobre estas interfaces estándar cuando corresponda, en vez de exigir files o byte slices concretos. `Read` puede devolver datos y un error como `io.EOF` en la misma llamada, así que sigue el contrato.
