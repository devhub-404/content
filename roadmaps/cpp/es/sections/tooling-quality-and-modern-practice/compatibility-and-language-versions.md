# Versiones del Lenguaje y Compatibilidad

C++ evoluciona mediante revisiones regulares, pero el soporte del compiler y standard library llega feature por feature. El proyecto debe definir un baseline mínimo y verificar las facilities exactas en vez de asumir que una flag `-std=` habilita todo en cualquier entorno.

```cpp
#if __cplusplus >= 202302L
    // C++23 language mode or later
#endif
```

Los feature-test macros protegen facilities opcionales mejor que comprobar versiones de compiler. Aísla código específico y prueba los compilers soportados en CI. Las features del working draft futuro no deben tratarse como C++ estable portable hasta entrar en tu baseline.
