# Fuzz Testing

El package testing incluye fuzzing que muta seed inputs para descubrir crashes, assumptions inválidas y edge cases. Es especialmente útil en parsers, encoders, protocols y funciones con un input space grande.

```go
func FuzzParse(f *testing.F) {
    f.Add("seed")

    f.Fuzz(func(t *testing.T, input string) {
        _ = Parse(input)
    })
}
```

Un buen fuzz target verifica invariantes, no solo ausencia de panic. Limita inputs cuando sea necesario, conserva regressions encontradas en el corpus y combina fuzzing con tests deterministas.
