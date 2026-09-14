# Funções e Múltiplos Retornos

Funções declaram parâmetros e resultados explicitamente e Go suporta múltiplos retornos. O caso mais comum é valor útil mais `error`, mas também há protocolos `(value, ok)` em lookups.

```go
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

Named results podem documentar assinatura complexa e interagir com `defer`, mas abuso torna fluxo menos óbvio. Prefira funções curtas e retornos explícitos salvo quando nomes realmente melhoram o contrato.
