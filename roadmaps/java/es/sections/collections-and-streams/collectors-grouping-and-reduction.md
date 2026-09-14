# Collectors, Grouping y Reduction

Los collectors describen reductions mutables hacia lists, maps, grupos, summaries, strings y aggregations. `groupingBy`, `partitioningBy`, `mapping` y downstream collectors expresan reportes ricos.

```java
Map<String, Long> counts = users.stream()
    .collect(Collectors.groupingBy(
        User::country,
        Collectors.counting()));
```

Los nests complejos pueden ser más difíciles que un pequeño accumulator imperativo. Nombra helpers o usa un loop cuando la expresión deje de comunicar la regla.
