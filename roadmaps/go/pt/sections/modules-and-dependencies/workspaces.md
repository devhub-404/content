# Go Workspaces

Workspace (`go.work`) permite que múltiplos modules locais participem do mesmo build sem publicar ou adicionar replace permanente em cada módulo. É útil para desenvolvimento coordenado.

```go
// go.work
go 1.27

use (
    ./service
    ./library
)
```

Workspace é construct de ambiente, não substitui correção independente de cada module. Teste modules também como consumers reais para o workspace não esconder dependency ausente ou module path incorreto.
