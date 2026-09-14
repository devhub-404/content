# `Iterable`, `Iterator` e Percurso

`Iterable` representa algo que produz iterator e enhanced `for` usa esse protocolo. `Iterator` expõe `hasNext`, `next` e removal opcional. Spliterators suportam traversal mais rico usado por streams.

```java
Iterator<String> it = names.iterator();
while (it.hasNext()) {
    String name = it.next();
    if (name.isBlank()) it.remove();
}
```

Use iterator removal apenas quando implementation suporta e mutation pertence ao traversal. Para transformações comuns, stream operations ou collection methods podem expressar melhor.
