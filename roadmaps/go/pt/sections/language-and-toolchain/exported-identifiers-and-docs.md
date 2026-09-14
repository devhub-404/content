# Identifiers Exportados e Documentação

Go usa capitalização para visibilidade entre packages: identifier iniciado por letra Unicode maiúscula é exportado. Isso torna a API pública visível diretamente no source sem um sistema separado de access modifiers.

```go
package geometry

// Point represents a location in 2D space.
type Point struct {
    X float64
    Y float64
}
```

Comentários de documentação em declarations exportadas fazem parte do design normal e aparecem em `go doc`/pkg.go.dev. Explique o contrato, não apenas repita o nome. Mantenha detalhes de implementação não exportados com nomes minúsculos.
