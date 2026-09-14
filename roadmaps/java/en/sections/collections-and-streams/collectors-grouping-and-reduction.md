# Collectors, Grouping, and Reduction

Collectors describe mutable reductions from a stream into lists, maps, grouped results, summaries, strings, and nested aggregation structures. `groupingBy`, `partitioningBy`, `mapping`, and downstream collectors can express rich reporting pipelines.

```java
Map<String, Long> counts = users.stream()
    .collect(Collectors.groupingBy(
        User::country,
        Collectors.counting()));
```

Complex collector nests can become harder to read than a small imperative accumulator. Name intermediate functions or use a domain-specific loop when the collector expression stops communicating the business rule clearly.
