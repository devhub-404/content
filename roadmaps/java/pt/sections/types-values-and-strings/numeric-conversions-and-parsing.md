# Conversões Numéricas e Parsing

Java permite algumas widening conversions implícitas e exige cast para narrowing. Cast pode truncar, então métodos como `Math.toIntExact` ajudam quando overflow deve falhar. Parsing de texto é separado de cast numérico.

```java
long wide = 42;
int narrow = Math.toIntExact(wide);

int value = Integer.parseInt("123");
double ratio = Double.parseDouble("0.75");
```

Em fronteiras externas, trate `NumberFormatException` conforme o contrato. Para dinheiro e decimal exato, use `BigDecimal` com scale/rounding explícitos em vez de `double`.
