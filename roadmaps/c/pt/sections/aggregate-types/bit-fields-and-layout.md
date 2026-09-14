# Bit-fields, Alignment e Layout

Bit-fields permitem que membros de struct ocupem um número especificado de bits, mas ordem, packing e alguns detalhes são implementation-defined. Podem servir a interfaces de hardware específicas, mas não são boa escolha padrão para formatos portáveis de rede ou arquivo.

```c
struct flags {
    unsigned ready : 1;
    unsigned error : 1;
    unsigned mode  : 2;
};
```

Para formatos binários externos, encode/decode explicitamente com máscaras e shifts e defina byte order. Use `alignof`, `alignas`, `sizeof` e static assertions quando o layout importar e verifique hipóteses em cada ABI suportada.
