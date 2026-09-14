# Variables, `final` y `var`

`var` pide al compilador inferir un tipo estático local desde el initializer. `final` impide reasignar el binding, pero una referencia final puede seguir apuntando a un objeto mutable.

```java
var name = "Mina";
final int maxRetries = 5;

name = name.toUpperCase();
```

Usa `var` cuando el tipo siga siendo obvio y tipos explícitos cuando la abstracción importe. `final` ayuda con invariantes y captures, pero Java no exige declarar final todo local que no cambie.
