# Collectors, Grouping e Reduction

Collectors descrevem reductions mutáveis para lists, maps, groups, summaries, strings e aggregations. `groupingBy`, `partitioningBy`, `mapping` e downstream collectors expressam relatórios ricos.

```java
Map<String, Long> counts = users.stream()
    .collect(Collectors.groupingBy(
        User::country,
        Collectors.counting()));
```

Nests complexos podem ficar mais difíceis que um accumulator imperativo pequeno. Nomeie helpers ou use loop quando a expressão deixa de comunicar a regra.
