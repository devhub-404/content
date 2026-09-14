# Portabilidad y Feature Detection

El C portable distingue el estándar del lenguaje de extensiones del compilador, APIs del sistema, assumptions de CPU y detalles ABI. Los feature-test macros y la configuración deben proteger capacidades opcionales en vez de adivinar por la marca del compilador.

```c
#if __STDC_VERSION__ >= 202311L
    /* C23-capable language mode */
#endif
```

Mantén código específico detrás de interfaces estrechas y compila el núcleo en modos estándar estrictos cuando sea posible. Comprueba anchuras enteras, endianness, alignment, filesystem, threads y contratos de librería donde la aplicación dependa de ellos.
