# Maps

Map é tipo reference built-in de chaves comparable para valores. Lookup de chave ausente retorna zero value; a forma com dois resultados informa se a chave estava presente.

```go
counts := map[string]int{
    "go": 2,
}

counts["rust"]++

value, ok := counts["missing"]
fmt.Println(value, ok)
```

Zero value de map é nil: pode ser lido, mas não receber assignments até `make`/literal. Ordem de iteração é unspecified. Maps não são seguros para writes concorrentes sem sincronização e a chave precisa ser comparable.
