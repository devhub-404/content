# Seleção Genérica com `_Generic`

`_Generic` seleciona uma expressão conforme o tipo de uma expressão controladora e é o principal mecanismo padrão para interfaces type-generic em C. Pode fornecer wrappers convenientes sobre famílias de funções tipadas sem dispatch de runtime.

```c
#define type_name(x) _Generic((x),     int: "int",                      double: "double",                default: "other")

printf("%s
", type_name(3.14));
```

Ainda é metaprogramação de compile time e pode ficar difícil de manter com muitos casos. Mantenha as funções reais visíveis e teste como qualifiers e conversions afetam o tipo controlado.
