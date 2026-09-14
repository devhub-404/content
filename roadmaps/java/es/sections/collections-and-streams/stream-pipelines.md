# Pipelines de Stream

Los streams describen pipelines lazy. Intermediate operations como `filter`/`map` construyen el pipeline y terminal operations como `toList`, `reduce` y `count` lo ejecutan. Un stream suele ser single-use.

```java
List<String> names = users.stream()
    .filter(User::active)
    .map(User::name)
    .sorted()
    .toList();
```

Los streams son excelentes para transformaciones/agregaciones cuando el flujo queda claro. No almacenan datos. Un loop suele ser mejor cuando dominan control flow, checked exceptions o side effects complejos.
