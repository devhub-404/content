# Type Erasure y Tipos en Runtime

La mayoría de type arguments se borra de la identidad runtime. Por eso no puedes hacer directamente `new T()`, `instanceof List<String>` o un generic array `new T[10]`.

```java
List<String> names = new ArrayList<>();
List<Integer> counts = new ArrayList<>();

System.out.println(names.getClass() == counts.getClass());
```

Cuando haga falta runtime type info, pasa `Class<T>`, una factory u otro descriptor explícito. No uses unchecked casts para fingir que la información borrada sigue existiendo.
