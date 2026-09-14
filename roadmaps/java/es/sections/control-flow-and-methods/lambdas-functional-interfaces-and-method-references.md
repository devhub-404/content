# Lambdas, Functional Interfaces y Method References

Una functional interface tiene un abstract method y puede implementarse mediante lambda o method reference. `java.util.function` ofrece `Predicate`, `Function`, `Consumer`, `Supplier` y otros shapes comunes.

```java
Predicate<String> nonEmpty = s -> !s.isEmpty();
Function<String, Integer> length = String::length;

names.stream()
    .filter(nonEmpty)
    .map(length)
    .forEach(System.out::println);
```

Las variables locales capturadas deben ser final o effectively final. Usa functional interfaces cuando el comportamiento se pase naturalmente como dato; métodos/classes normales son mejores para responsabilidades stateful grandes.
