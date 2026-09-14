# Type Erasure e Tipos em Runtime

A maioria dos type arguments é apagada da identidade runtime. Por isso não é possível fazer diretamente `new T()`, `instanceof List<String>` ou generic array `new T[10]`.

```java
List<String> names = new ArrayList<>();
List<Integer> counts = new ArrayList<>();

System.out.println(names.getClass() == counts.getClass());
```

Quando runtime type info é necessária, passe `Class<T>`, factory ou descriptor explícito. Não use unchecked casts para fingir que informação apagada ainda existe.
