# `typedef` y Nombres de Tipo

`typedef` crea otro nombre para un tipo existente; no crea un tipo nominalmente distinto. Es útil para simplificar declaraciones verbosas, nombrar firmas de function pointers y presentar tipos de librería sin repetir su forma de implementación.

```c
typedef struct {
    double x;
    double y;
} point;

point p = { .x = 1.0, .y = 2.0 };
```

Un typedef puede mejorar o esconder información. Evita ocultar ownership de punteros o constness tras aliases sorprendentes. Los typedefs públicos deben comunicar una abstracción estable, no solo ahorrar caracteres.
