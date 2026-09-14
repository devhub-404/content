# Packages e Imports

Todo source Go pertence a um package, e packages são unidade de compilação e organização de namespace. Arquivos no mesmo package contribuem para o mesmo package scope, enquanto imports tornam identifiers exportados de outros packages disponíveis pelo nome do package.

```go
package report

import (
    "fmt"
    "time"
)

func PrintNow() {
    fmt.Println(time.Now())
}
```

O nome do package deve descrever uma responsabilidade coerente. Import cycles são proibidos, favorecendo grafos dirigidos de dependência. Mantenha APIs pequenas e evite buckets genéricos como `util` quando as funções pertencem a domínios mais claros.
