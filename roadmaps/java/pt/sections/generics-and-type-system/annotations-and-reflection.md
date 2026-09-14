# Annotations e Reflection

Annotations anexam metadata a declarations/type uses, enquanto reflection inspeciona classes, methods, fields, constructors, generics e annotations em runtime. Frameworks usam ambos para serialization, DI, testing e persistence.

```java
@Deprecated
public void oldApi() { }

Class<?> type = User.class;
for (var method : type.getDeclaredMethods()) {
    System.out.println(method.getName());
}
```

Reflection troca safety de compile time e performance por flexibilidade. Prefira chamadas tipadas quando tipos são conhecidos e cache metadata repetida em infraestrutura reflection-heavy.
