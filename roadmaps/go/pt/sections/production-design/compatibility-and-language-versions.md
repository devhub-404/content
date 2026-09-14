# Versões da Linguagem e Compatibilidade

Modules declaram uma versão Go que controla semântica esperada da linguagem. Toolchains evoluem separadamente e versões novas podem compilar modules direcionados a versões anteriores compatíveis.

```go
// go.mod
module example.com/project

go 1.27
```

Ao usar feature nova, verifique se é de linguagem, standard library ou toolchain e qual minimum version exige. Mantenha a versão declarada honesta para consumers e tooling receberem sinal correto.
