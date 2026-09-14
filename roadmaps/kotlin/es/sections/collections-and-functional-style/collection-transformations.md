# Transformaciones de Collections

La standard library ofrece `map`, `filter`, `associate`, `groupBy`, `partition`, `fold`, `zip` y sorting. En collections normales, las operaciones suelen ser eager y crean resultados intermedios.

```kotlin
val activeNames = users
    .filter { it.active }
    .map { it.name }
    .sorted()
```

Las chains son claras, pero pueden asignar intermedios. Para datasets grandes o short-circuit, `Sequence` o un loop puede reducir trabajo si las mediciones lo justifican.
