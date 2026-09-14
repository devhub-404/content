# Fuzz Testing

Package testing inclui fuzzing que muta seed inputs para descobrir crashes, assumptions inválidas e edge cases. É especialmente útil em parsers, encoders, protocols e funções com input space grande.

```go
func FuzzParse(f *testing.F) {
    f.Add("seed")

    f.Fuzz(func(t *testing.T, input string) {
        _ = Parse(input)
    })
}
```

Um bom fuzz target verifica invariantes, não apenas ausência de panic. Limite inputs quando necessário, preserve regressions descobertas no corpus e combine fuzzing com tests determinísticos.
