# Loops y Enhanced `for`

Java ofrece `for`, enhanced `for`, `while` y `do`. Enhanced `for` funciona con arrays e `Iterable` y suele ser la forma más clara cuando el índice no importa.

```java
for (String name : names) {
    System.out.println(name);
}

for (int i = 0; i < names.size(); i++) {
    System.out.println(i + ": " + names.get(i));
}
```

Usa iterator o índice explícito cuando importen mutation, removal o posición. La modificación estructural de muchas collections durante enhanced-for puede producir `ConcurrentModificationException`.
