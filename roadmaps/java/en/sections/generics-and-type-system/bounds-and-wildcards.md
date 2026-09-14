# Bounds and Wildcards

Bounds restrict type parameters, while wildcards describe variance-like relationships at use sites. `? extends T` is useful for producers you mainly read from, and `? super T` for consumers you mainly write T values into—the common PECS guideline.

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

Wildcards can make signatures expressive but difficult when nested deeply. Prefer a named generic method or a simpler domain interface when a public API starts exposing several layers of wildcard logic.
