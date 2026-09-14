# `const`, `volatile` y `restrict`

`const` impide modificar a través de un determinado tipo de lvalue; no significa necesariamente que el objeto subyacente nunca cambie por otra vía permitida. `volatile` afecta los accesos a objetos volatile y sirve para casos especiales de hardware o señales, no para sincronización general entre threads.

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

`restrict` es una promesa sobre aliasing asociada a accesos mediante punteros, lo que permite optimizaciones más fuertes si se cumple. Romper ese contrato puede producir undefined behavior. Usa qualifiers para expresar contratos reales de interfaz, no como decoración.
