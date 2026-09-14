# Métodos, Overloading y Parámetros

Los métodos declaran tipos de parámetros/retorno y Java soporta overloads elegidos por firma y reglas de conversión. Java pasa argumentos por valor: los parámetros de objeto reciben una copia de la referencia, pudiendo mutar el objeto pero no rebindear la variable del caller.

```java
static int max(int a, int b) {
    return a >= b ? a : b;
}

static double max(double a, double b) {
    return a >= b ? a : b;
}
```

Mantén los overloads semánticamente consistentes. Java no tiene default arguments, así que builders, overloads u objetos de configuración son comunes para opciones.
