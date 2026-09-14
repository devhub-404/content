# Interfaces Nil y Valores Nil Tipados

Un valor interface contiene conceptualmente un tipo dinámico y un valor dinámico. La interface solo es nil cuando ambos están ausentes. Guardar un typed nil pointer produce una interface non-nil, fuente común de checks sorprendentes.

```go
var p *bytes.Buffer = nil
var w io.Writer = p

fmt.Println(w == nil) // false
```

Retorna nil literal cuando el resultado interface esté realmente ausente. Evita envolver punteros nil tipados sin intención e inspecciona el dynamic type al depurar una interface non-nil con puntero subyacente nil.
