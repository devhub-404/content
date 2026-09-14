# Funciones y Múltiples Resultados

Las funciones declaran parámetros y resultados explícitamente y Go soporta múltiples retornos. El caso más común es valor útil más `error`, aunque también existen protocolos `(value, ok)` en lookups.

```go
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

Los named results pueden documentar una firma compleja e interactuar con `defer`, pero abusar de ellos hace menos obvio el flujo. Prefiere funciones cortas y retornos explícitos salvo que los nombres mejoren realmente el contrato.
