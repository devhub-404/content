# Race Detector y `go vet`

El race detector instrumenta el build para encontrar accesos conflictivos sin sincronización durante ejecución. `go vet` hace checks estáticos de construcciones legales pero frecuentemente erróneas.

```go
// Typical checks:
// go test -race ./...
// go vet ./...
```

Ambos son herramientas normales, no sustitutos de tests/review. El race detector solo ve rutas ejecutadas y cambia timing; vet no intenta demostrar todo bug. Ejecútalos regularmente para mantener los fallos cerca del cambio que los introdujo.
