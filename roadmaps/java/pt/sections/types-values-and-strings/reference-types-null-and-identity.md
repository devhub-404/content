# Reference Types, `null` e Identidade

Classes, interfaces e arrays são reference types e podem ser `null`. `==` compara identidade de referência, enquanto `equals` é o contrato convencional para igualdade lógica quando o tipo o define.

```java
String first = new String("hello");
String second = new String("hello");

System.out.println(first == second);      // identity
System.out.println(first.equals(second)); // value contract
```

Null faz parte normal de reference types, então APIs precisam documentar ausência. Prefira `Objects.requireNonNull`, validação ou `Optional` em fronteiras selecionadas a deixar null inesperado viajar pelo sistema.
