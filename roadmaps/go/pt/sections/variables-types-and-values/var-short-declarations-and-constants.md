# `var`, Declaração Curta e Constants

`var` declara variáveis explicitamente e pode inferir tipo pelo initializer. Dentro de funções, `:=` é a forma curta e precisa declarar ao menos uma variável nova no scope atual. Constants são valores de compile time com regras próprias de representabilidade e untyped constants.

```go
var host string = "example.com"
port := 443

const timeoutSeconds = 30
const Pi = 3.141592653589793
```

Use short declarations para locals quando o tipo é óbvio, mas fique atento a shadowing em scopes aninhados. Constants podem permanecer untyped até o contexto definir um tipo concreto, tornando constantes numéricas flexíveis.
