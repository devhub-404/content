# Bounds y Wildcards

Los bounds restringen type parameters, mientras wildcards describen relaciones en use sites. `? extends T` sirve para producers que lees y `? super T` para consumers que reciben T, resumido por PECS.

```java
static double total(List<? extends Number> values) {
    double sum = 0;
    for (Number value : values) sum += value.doubleValue();
    return sum;
}

static void addDefaults(List<? super Integer> values) {
    values.add(0);
}
```

Los wildcards pueden ser expresivos pero difíciles si se anidan. Prefiere un generic method nombrado o una interfaz de dominio cuando una API pública empiece a exponer lógica de wildcards profunda.
