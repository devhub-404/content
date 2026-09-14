# Loops and Enhanced `for`

Java provides `for`, enhanced `for`, `while`, and `do` loops. Enhanced `for` works with arrays and `Iterable` values and is normally clearest when the index itself is irrelevant.

```java
for (String name : names) {
    System.out.println(name);
}

for (int i = 0; i < names.size(); i++) {
    System.out.println(i + ": " + names.get(i));
}
```

Use iterators or explicit indexes when mutation, removal, or position matters. Structural modification of many collections while an ordinary enhanced-for iterator is active can trigger fail-fast behavior such as `ConcurrentModificationException`.
