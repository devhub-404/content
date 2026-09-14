# `range` sobre Coleções e Iterators

`range` itera arrays, slices, strings, maps, channels, inteiros no Go moderno e iterator functions suportadas. Os valores produzidos dependem da expressão; range de string não é byte indexing e a ordem de map é unspecified.

```go
for index, value := range values {
    fmt.Println(index, value)
}

for key, value := range lookup {
    fmt.Println(key, value)
}
```

Entenda quando a variável é cópia. Para mutar elementos de slice, indexação costuma ser mais clara. Nunca dependa da ordem de iteração de map sem ordenar as chaves explicitamente.
