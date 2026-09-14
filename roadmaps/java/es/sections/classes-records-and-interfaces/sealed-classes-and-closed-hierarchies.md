# Sealed Classes y Jerarquías Cerradas

Una sealed class/interface restringe qué tipos pueden extend/implement. Las subclases permitidas deben continuar explícitamente como `final`, `sealed` o `non-sealed`, creando una jerarquía controlada.

```java
public sealed interface Result
    permits Success, Failure { }

record Success(String value) implements Result { }
record Failure(String message) implements Result { }
```

Las jerarquías sealed son excelentes para alternativas de dominio cerradas y switch exhaustivo. Usa interfaces abiertas cuando implementaciones de terceros formen parte del extension model.
