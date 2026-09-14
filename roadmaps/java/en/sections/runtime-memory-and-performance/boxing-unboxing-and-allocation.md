# Boxing, Unboxing, and Allocation

Boxing converts primitive values to wrapper objects and unboxing converts wrappers back to primitives. Generic collections historically store reference types, so collections such as `List<Integer>` involve wrapper values rather than an `int` specialization in ordinary Java 25.

```java
Integer boxed = 42;
int value = boxed;

List<Integer> values = List.of(1, 2, 3);
```

Do not optimize every boxing operation by instinct, but be aware of allocation and null-unboxing risks in hot numeric paths. Profile before redesigning APIs around primitive arrays or specialized libraries.
