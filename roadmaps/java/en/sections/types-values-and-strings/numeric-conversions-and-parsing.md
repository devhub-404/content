# Numeric Conversions and Parsing

Java allows some widening primitive conversions implicitly and requires casts for narrowing conversions. A cast can truncate values, so library methods such as `Math.toIntExact` are useful when overflow should fail instead of silently narrowing. Parsing text is separate from numeric casting.

```java
long wide = 42;
int narrow = Math.toIntExact(wide);

int value = Integer.parseInt("123");
double ratio = Double.parseDouble("0.75");
```

At trust boundaries, catch or prevent `NumberFormatException` according to the input contract. For money and exact decimal calculations, use `BigDecimal` with explicit scale and rounding policies rather than `double`.
