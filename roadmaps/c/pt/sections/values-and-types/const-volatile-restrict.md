# `const`, `volatile` e `restrict`

`const` impede modificação por um determinado tipo de lvalue; não significa necessariamente que o objeto subjacente nunca muda por outro caminho permitido. `volatile` afeta os acessos a objetos volatile e serve a casos especiais de hardware ou sinais, não a sincronização geral entre threads.

```c
void scale(size_t n,
           double *restrict out,
           const double *restrict in,
           double factor) {
    for (size_t i = 0; i < n; ++i) {
        out[i] = in[i] * factor;
    }
}
```

`restrict` é uma promessa sobre aliasing associada a acessos por ponteiro, permitindo otimizações mais fortes quando suas regras são cumpridas. Quebrar esse contrato pode gerar undefined behavior. Use qualifiers para expressar contratos reais de interface, não como decoração.
