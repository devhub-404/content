# Portabilidade e Feature Detection

C portável distingue o padrão da linguagem de extensões do compilador, APIs do sistema, assumptions de CPU e detalhes de ABI. Feature-test macros e configuração devem proteger capacidades opcionais em vez de adivinhar por marca do compilador.

```c
#if __STDC_VERSION__ >= 202311L
    /* C23-capable language mode */
#endif
```

Mantenha código específico atrás de interfaces estreitas e compile o core em modos estritos quando possível. Teste larguras inteiras, endianness, alignment, filesystem, threads e contratos de biblioteca onde a aplicação depender disso.
