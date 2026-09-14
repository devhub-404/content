# Macros e Compilação Condicional

O preprocessador transforma tokens antes da compilação C. Macros object-like e function-like substituem tokens, e diretivas condicionais escolhem source conforme macros ou condições da implementação.

```c
#define ARRAY_COUNT(a) (sizeof(a) / sizeof((a)[0]))

#if defined(_WIN32)
    /* Windows-specific code */
#else
    /* portable/POSIX path */
#endif
```

Macros não são funções tipadas: argumentos podem ser avaliados várias vezes e precedência pode mudar sem parênteses adequados. Prefira funções, `static inline`, enums ou constantes quando resolverem o mesmo problema. Use compilação condicional para isolar diferenças reais de plataforma.
