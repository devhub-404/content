# Tipos Primitivos

Java tiene ocho tipos primitivos: cuatro enteros, dos floating-point, `char` y `boolean`. Los primitivos no son objetos, aunque boxing puede envolverlos en clases como `Integer` cuando se requiere un objeto.

```java
int count = 42;
long population = 8_000_000_000L;
double ratio = 0.75;
boolean ready = true;
char letter = 'A';
```

Elige según rango y contrato. `int` es el entero general, `long` sirve a rangos mayores y floating-point no es aritmética decimal exacta para dinero.
