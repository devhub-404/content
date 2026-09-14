# Stream Pipelines

Streams describe lazy pipelines over data sources. Intermediate operations such as `filter` and `map` build a pipeline, while terminal operations such as `toList`, `reduce`, `count`, or `forEach` execute it. A stream is normally single-use.

```java
List<String> names = users.stream()
    .filter(User::active)
    .map(User::name)
    .sorted()
    .toList();
```

Streams are ideal for transformations and aggregations where the data flow is clearer than manual mutation. They are not collections and do not store data themselves. A loop is often clearer when control flow, checked exceptions, or complex side effects dominate.
