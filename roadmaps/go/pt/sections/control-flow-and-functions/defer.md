# `defer` e Cleanup

`defer` agenda uma chamada para executar quando a função ao redor retornar. Deferred calls executam em ordem LIFO e seus argumentos são avaliados no momento do `defer`.

```go
file, err := os.Open(path)
if err != nil {
    return err
}
defer file.Close()

// use file
```

`defer` coloca cleanup perto da aquisição e funciona com early returns, sendo idiom central de resource management. Mantenha recursos long-lived em scopes de função adequados para o cleanup ocorrer na hora desejada.
