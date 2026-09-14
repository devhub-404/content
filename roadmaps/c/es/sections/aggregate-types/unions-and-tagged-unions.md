# Unions y Tagged Unions

Una union superpone varios miembros en el mismo almacenamiento. En cada punto lógico el programa debe saber qué representación está activa y qué accesos permite el lenguaje. Las unions sirven para variants compactos y trabajo de representación de bajo nivel.

```c
enum value_kind { VALUE_INT, VALUE_DOUBLE };

struct value {
    enum value_kind kind;
    union {
        int as_int;
        double as_double;
    } data;
};
```

Una tagged union combina la union con un discriminador explícito para seleccionar el miembro correcto. Mantén tag y payload sincronizados. Es el equivalente C de un variant algebraico, pero el compilador no garantiza exhaustividad ni consistencia automáticamente.
