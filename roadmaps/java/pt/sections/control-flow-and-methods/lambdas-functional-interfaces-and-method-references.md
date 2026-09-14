# Lambdas, Functional Interfaces e Method References

Functional interface tem um abstract method e pode ser implementada por lambda ou method reference. `java.util.function` fornece `Predicate`, `Function`, `Consumer`, `Supplier` e outros shapes comuns.

```java
Predicate<String> nonEmpty = s -> !s.isEmpty();
Function<String, Integer> length = String::length;

names.stream()
    .filter(nonEmpty)
    .map(length)
    .forEach(System.out::println);
```

Variáveis locais capturadas precisam ser final ou effectively final. Use functional interfaces quando comportamento é naturalmente passado como dado; métodos/classes comuns são melhores para responsabilidades stateful grandes.
