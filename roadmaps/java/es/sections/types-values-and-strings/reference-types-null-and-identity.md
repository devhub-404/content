# Reference Types, `null` e Identidad

Classes, interfaces y arrays son reference types y pueden ser `null`. `==` compara identidad de referencia, mientras `equals` es el contrato convencional para igualdad lógica cuando el tipo lo define.

```java
String first = new String("hello");
String second = new String("hello");

System.out.println(first == second);      // identity
System.out.println(first.equals(second)); // value contract
```

Null forma parte normal de reference types, así que las APIs deben documentar ausencia. Prefiere `Objects.requireNonNull`, validación u `Optional` en fronteras seleccionadas en vez de dejar que null inesperado viaje por el sistema.
