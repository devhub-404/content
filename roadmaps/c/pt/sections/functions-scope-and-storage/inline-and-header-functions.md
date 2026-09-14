# `inline` e Funções Definidas em Header

O specifier `inline` participa das regras de definições e linkage; não é um comando que força o compilador a inlinear machine code. O otimizador pode inlinear sem a keyword ou recusar mesmo quando ela aparece.

```c
static inline int min_int(int a, int b) {
    return a < b ? a : b;
}
```

Para helpers pequenos definidos em headers, `static inline` é um padrão comum porque cada translation unit recebe uma definição com internal linkage. Padrões de external inline são mais sutis e só devem ser usados quando o projeto realmente precisa.
