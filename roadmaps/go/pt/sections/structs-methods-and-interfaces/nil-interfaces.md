# Interfaces Nil e Valores Nil Tipados

Valor interface contém conceitualmente tipo dinâmico e valor dinâmico. A interface só é nil quando ambos estão ausentes. Guardar typed nil pointer produz interface non-nil, fonte comum de checks surpreendentes.

```go
var p *bytes.Buffer = nil
var w io.Writer = p

fmt.Println(w == nil) // false
```

Retorne nil literal quando resultado interface realmente está ausente. Evite envolver ponteiros nil tipados sem intenção e inspecione o dynamic type ao depurar interface non-nil com pointer subjacente nil.
