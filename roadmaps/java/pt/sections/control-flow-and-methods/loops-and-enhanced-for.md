# Loops e Enhanced `for`

Java fornece `for`, enhanced `for`, `while` e `do`. Enhanced `for` funciona com arrays e `Iterable` e é a forma mais clara quando índice não importa.

```java
for (String name : names) {
    System.out.println(name);
}

for (int i = 0; i < names.size(); i++) {
    System.out.println(i + ": " + names.get(i));
}
```

Use iterator ou índice explícito quando mutation, removal ou posição importam. Modificação estrutural de muitas collections durante enhanced-for pode gerar `ConcurrentModificationException`.
