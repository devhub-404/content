# Versões da Linguagem e Compatibilidade

C++ evolui por revisões regulares, mas suporte do compiler e standard library chega feature por feature. O projeto deve definir baseline mínimo e verificar facilities exatas em vez de assumir que uma flag `-std=` habilita tudo em todo lugar.

```cpp
#if __cplusplus >= 202302L
    // C++23 language mode or later
#endif
```

Feature-test macros protegem facilities opcionais melhor que checar versão do compiler. Isole código específico e teste compilers suportados em CI. Features do working draft futuro não devem ser tratadas como C++ estável portável até entrarem no baseline.
