# Conversiones Numéricas y Parsing

Java permite algunas widening conversions implícitas y exige cast para narrowing. Un cast puede truncar, por lo que métodos como `Math.toIntExact` ayudan cuando el overflow debe fallar. Parsear texto es distinto de hacer cast numérico.

```java
long wide = 42;
int narrow = Math.toIntExact(wide);

int value = Integer.parseInt("123");
double ratio = Double.parseDouble("0.75");
```

En fronteras externas, maneja `NumberFormatException` según el contrato. Para dinero y decimales exactos, usa `BigDecimal` con scale/rounding explícitos en vez de `double`.
