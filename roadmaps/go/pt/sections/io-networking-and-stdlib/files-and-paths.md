# Arquivos e Paths

Package `os` expõe files, environment e recursos do sistema, enquanto `path/filepath` manipula filesystem paths com separadores nativos. `path` serve a caminhos slash-based como URLs, não ao filesystem local em geral.

```go
data, err := os.ReadFile("config.json")
if err != nil {
    return err
}

path := filepath.Join("data", "report.txt")
fmt.Println(path, len(data))
```

`os.ReadFile` é ótimo para arquivos bounded; streaming por `os.File` é melhor para grandes dados. Cheque erros de open/read/write/sync/close quando durability importa. Filesystem pode mudar por ações externas.
