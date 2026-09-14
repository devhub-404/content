# Bounds e Wildcards

Bounds restringem type parameters, enquanto wildcards descrevem relações nos use sites. `? extends T` funciona para producers lidos e `? super T` para consumers que recebem T, resumido por PECS.

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

Wildcards podem expressar muito, mas ficam difíceis quando aninhados. Prefira generic method nomeado ou interface de domínio quando API pública começa a expor lógica de wildcard profunda.
