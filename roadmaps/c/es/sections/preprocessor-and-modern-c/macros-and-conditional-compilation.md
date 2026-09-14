# Macros y Compilación Condicional

El preprocesador transforma tokens antes de la compilación C. Las macros object-like y function-like sustituyen tokens, y las directivas condicionales seleccionan source según macros o condiciones de implementación.

```c
#define ARRAY_COUNT(a) (sizeof(a) / sizeof((a)[0]))

#if defined(_WIN32)
    /* Windows-specific code */
#else
    /* portable/POSIX path */
#endif
```

Las macros no son funciones tipadas: sus argumentos pueden evaluarse varias veces y la precedencia puede cambiar sin paréntesis adecuados. Prefiere funciones, `static inline`, enums o constantes cuando resuelvan lo mismo. Usa compilación condicional para aislar diferencias reales de plataforma.
