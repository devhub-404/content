# Primitive Types

Java has eight primitive types: four integer sizes, two floating-point types, `char`, and `boolean`. Primitive values are not objects, although boxing can wrap them in classes such as `Integer` and `Double` when an object is required.

```java
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
boolean ready = true;
char letter = 'A';
```

Choose the type from range and API needs. `int` is the general-purpose integer, `long` is common for larger counts and epoch-like quantities, and floating-point types are not exact decimal arithmetic for money.
