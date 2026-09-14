# `typeof`, `auto` e Inferencia de Tipo en C23

C23 añade mecanismos estandarizados de inferencia y consulta de tipos, incluidos `auto` en declaraciones inferidas y `typeof`/`typeof_unqual`. Reducen repetición cuando el tipo ya viene determinado por el initializer o la expresión.

```c
auto x = 42;
typeof(x) y = 7;
typeof_unqual(x) z = 9;
```

Esto no convierte C en un lenguaje dinámico: el compilador sigue determinando un tipo estático durante la traducción. Usa inferencia cuando elimine duplicación frágil sin ocultar un tipo importante de interfaz y presta atención a qualifiers y conversiones.
