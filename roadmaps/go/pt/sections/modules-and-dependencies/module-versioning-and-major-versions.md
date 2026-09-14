# Versionamento de Modules e Major Versions

Modules publicados seguem semantic versioning, e v2+ normalmente inclui major suffix no module/import path. Isso permite coexistência de majors incompatíveis no mesmo build graph.

```go
// v1 import:
import "example.com/lib"

// v2+ import:
import "example.com/lib/v2"
```

Não altere tag publicada. Lance nova versão e preserve backward compatibility dentro de major quando possível. Package paths, identifiers exportados, interfaces e comportamento participam da compatibilidade.
