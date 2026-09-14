# `List`, `Set` e `Map`

Collections Framework gira em torno de `List`, `Set`, `Map`, `Queue` e `Deque`, com implementations para diferentes padrões de ordering, lookup e mutation. Programe contra interface quando caller não precisa do implementation detail.

```java
List<String> names = new ArrayList<>();
names.add("Mina");

Set<String> tags = new HashSet<>();
tags.add("java");

Map<String, Integer> counts = new HashMap<>();
counts.put("ready", 2);
```

Escolha primeiro pela semântica: list preserva sequência, set garante unicidade, map associa keys e sorted variants impõem ordering. Saiba se a implementação permite null.
