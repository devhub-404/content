# Tipos Básicos e Conversões

Go possui tipos inteiros, floating-point, complex, boolean, string e tipos relacionados a byte/rune. Há `int`/`uint` dependentes da máquina e nomes fixed-width como `int32` e `uint64`. Tipos nomeados são distintos mesmo com mesma representação subjacente.

```go
var age int = 42
var ratio float64 = 0.75
var enabled bool = true
var text string = "Go"

converted := float64(age)
```

Go não faz conversões numéricas implícitas amplas como linguagens C-like. Conversões são explícitas, tornando mudanças de sinal/precisão visíveis. Use `int` para counts/indexes comuns salvo quando protocolo ou range exige largura específica.
