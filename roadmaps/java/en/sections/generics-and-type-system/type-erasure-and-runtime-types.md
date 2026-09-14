# Type Erasure and Runtime Types

Most generic type arguments are erased from ordinary runtime class identity. This is why you cannot directly create `new T()`, test `value instanceof List<String>`, or create a generic array such as `new T[10]` without another mechanism.

```java
List<String> names = new ArrayList<>();
List<Integer> counts = new ArrayList<>();

System.out.println(names.getClass() == counts.getClass());
```

When runtime type information is required, pass a `Class<T>`, a factory, or another explicit descriptor. Do not use unchecked casts merely to pretend erased information still exists.
