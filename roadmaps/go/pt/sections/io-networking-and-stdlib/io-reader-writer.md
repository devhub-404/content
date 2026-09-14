# `io.Reader` e `io.Writer`

`io.Reader` e `io.Writer` são interfaces pequenas que conectam grande parte do ecossistema. Arquivos, buffers, network connections, compressors, hashers e HTTP bodies podem ser compostos por compartilharem esses contratos.

```go
func copyToFile(
    dst io.Writer,
    src io.Reader,
) error {
    _, err := io.Copy(dst, src)
    return err
}
```

Projete streaming APIs sobre interfaces padrão quando adequado, em vez de exigir files ou byte slices concretos. `Read` pode retornar dados e erro como `io.EOF` na mesma chamada, então siga o contrato.
