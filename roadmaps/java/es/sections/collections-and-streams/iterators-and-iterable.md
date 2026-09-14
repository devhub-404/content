# `Iterable`, `Iterator` y Recorrido

 `Iterable` representa algo que produce un iterator y enhanced `for` usa ese protocolo. `Iterator` expone `hasNext`, `next` y removal opcional. Los spliterators soportan recorrido más rico usado por streams.

```java
Iterator<String> it = names.iterator();
while (it.hasNext()) {
    String name = it.next();
    if (name.isBlank()) it.remove();
}
```

Usa iterator removal solo cuando la implementation lo soporte y la mutation pertenezca al recorrido. Para transformaciones normales, stream operations o collection methods pueden expresar mejor.
