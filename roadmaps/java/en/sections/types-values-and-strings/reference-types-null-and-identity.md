# Reference Types, `null`, and Identity

Class, interface, array, and other reference values refer to objects or can be `null`. The `==` operator compares reference identity for objects, while `equals` is the conventional method for logical equality when a type defines it.

```java
String first = new String("hello");
String second = new String("hello");

System.out.println(first == second);      // identity
System.out.println(first.equals(second)); // value contract
```

Null remains a normal part of Java reference types, so APIs must document absence clearly. Prefer `Objects.requireNonNull`, validation, or `Optional` at selected return boundaries rather than allowing unexpected nulls to travel deeply through the program.
