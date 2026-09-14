# `range` sobre Colecciones e Iterators

`range` itera arrays, slices, strings, maps, channels, enteros en Go moderno e iterator functions soportadas. Los valores producidos dependen de la expresión; range sobre string no equivale a byte indexing y el orden de map es unspecified.

```go
for index, value := range values {
    fmt.Println(index, value)
}

for key, value := range lookup {
    fmt.Println(key, value)
}
```

Entiende cuándo la variable es una copia. Para mutar elementos de un slice, la indexación suele ser más clara. No dependas del orden de iteración de un map sin ordenar las claves explícitamente.
