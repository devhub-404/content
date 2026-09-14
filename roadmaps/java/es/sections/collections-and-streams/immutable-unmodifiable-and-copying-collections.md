# Collections Unmodifiable y Copias

Factories como `List.of`, `Set.of` y `Map.of` crean collections unmodifiable, y `copyOf` crea una copia snapshot-like según contrato. Esto impide mutation estructural de la collection, pero no deep-freeze de sus elementos.

```java
List<String> names = List.of("Ada", "Mina");
List<String> snapshot = List.copyOf(source);
```

Úsalas en constants, retornos y boundaries donde los callers no deban mutar. Distingue una unmodifiable view de una copia independiente cuando cambios en la backing collection puedan filtrarse.
