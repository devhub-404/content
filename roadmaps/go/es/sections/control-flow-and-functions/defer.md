# `defer` y Cleanup

`defer` programa una llamada para ejecutarse cuando la función envolvente retorna. Las deferred calls se ejecutan en orden LIFO y sus argumentos se evalúan en el momento del `defer`.

```go
file, err := os.Open(path)
if err != nil {
    return err
}
defer file.Close()

// use file
```

`defer` coloca el cleanup junto a la adquisición y funciona con early returns, siendo un idiom central de gestión de recursos. Mantén recursos long-lived en scopes de función adecuados para que el cleanup ocurra cuando corresponde.
