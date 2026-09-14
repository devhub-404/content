# Collections Unmodifiable e Cópias

Factories como `List.of`, `Set.of` e `Map.of` criam collections unmodifiable, e `copyOf` cria cópia snapshot-like conforme contrato. Isso impede mutation estrutural pela collection, mas não deep-freeze dos elementos.

```java
List<String> names = List.of("Ada", "Mina");
List<String> snapshot = List.copyOf(source);
```

Use em constants, retornos e boundaries onde callers não devem mutar. Diferencie unmodifiable view de cópia independente quando mudanças na backing collection podem aparecer.
