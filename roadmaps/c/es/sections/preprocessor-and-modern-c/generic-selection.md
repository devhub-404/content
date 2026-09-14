# Selección Genérica con `_Generic`

`_Generic` selecciona una expresión según el tipo de una expresión controladora y es el principal mecanismo estándar para interfaces type-generic en C. Puede crear wrappers cómodos sobre familias de funciones tipadas sin dispatch de runtime.

```c
#define type_name(x) _Generic((x),     int: "int",                      double: "double",                default: "other")

printf("%s
", type_name(3.14));
```

Sigue siendo metaprogramación de compile time y puede volverse difícil con demasiados casos. Mantén visibles las funciones reales y comprueba cómo qualifiers y conversiones afectan al tipo controlador.
