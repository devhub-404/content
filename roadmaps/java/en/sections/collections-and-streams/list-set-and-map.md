# `List`, `Set`, and `Map`

The Collections Framework centers on interfaces such as `List`, `Set`, `Map`, `Queue`, and `Deque`, with implementations optimized for different ordering, lookup, and mutation patterns. Program to the interface when callers do not need implementation-specific features.

```java
List<String> names = new ArrayList<>();
names.add("Mina");

Set<String> tags = new HashSet<>();
tags.add("java");

Map<String, Integer> counts = new HashMap<>();
counts.put("ready", 2);
```

Choose based on semantics before complexity folklore: lists preserve sequence order, sets enforce uniqueness, maps associate keys with values, and sorted variants impose ordering contracts. Know whether nulls are permitted by the chosen implementation.
