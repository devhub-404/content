# Boxing, Unboxing e Allocation

Boxing converte primitive em wrapper e unboxing faz o inverso. Generic collections armazenam reference types, então `List<Integer>` usa wrappers, não specialization de `int` em Java 25 comum.

```java
Integer boxed = 42;
int value = boxed;

List<Integer> values = List.of(1, 2, 3);
```

Não otimize todo boxing por instinto, mas conheça allocation e risco de unbox de null em hot paths. Profile antes de redesenhar APIs com primitive arrays ou libraries especializadas.
