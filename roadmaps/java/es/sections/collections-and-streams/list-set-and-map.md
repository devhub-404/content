# `List`, `Set` y `Map`

Collections Framework gira alrededor de `List`, `Set`, `Map`, `Queue` y `Deque`, con implementations para distintos patrones de ordering, lookup y mutation. Programa contra la interfaz cuando el caller no necesite detalles de implementación.

```java
List<String> names = new ArrayList<>();
names.add("Mina");

Set<String> tags = new HashSet<>();
tags.add("java");

Map<String, Integer> counts = new HashMap<>();
counts.put("ready", 2);
```

Elige primero por semántica: list conserva secuencia, set garantiza unicidad, map asocia keys y sorted variants imponen ordering. Comprueba si la implementación permite null.
