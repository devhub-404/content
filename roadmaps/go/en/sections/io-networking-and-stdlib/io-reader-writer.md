# `io.Reader` and `io.Writer`

`io.Reader` and `io.Writer` are tiny interfaces that connect a large part of the Go ecosystem. Files, buffers, network connections, compressors, hashers, and HTTP bodies can often be composed because they share these contracts.

```go
func copyToFile(
    dst io.Writer,
    src io.Reader,
) error {
    _, err := io.Copy(dst, src)
    return err
}
```

Design streaming APIs around these standard interfaces when appropriate instead of requiring concrete files or byte slices. A `Read` call may return both data and an error such as `io.EOF`, so follow the interface contract rather than assuming error and byte count are mutually exclusive.
