# `typedef` e Nomes de Tipo

`typedef` cria outro nome para um tipo existente; não cria um tipo nominalmente distinto. É útil para abreviar declarações verbosas, nomear assinaturas de function pointers e apresentar tipos de biblioteca sem repetir a forma de implementação.

```c
typedef struct {
    double x;
    double y;
} point;

point p = { .x = 1.0, .y = 2.0 };
```

Um typedef pode melhorar ou esconder informação. Evite disfarçar ownership de ponteiros ou constness atrás de aliases surpreendentes. Typedefs públicos devem comunicar abstração estável, não apenas economizar alguns caracteres.
