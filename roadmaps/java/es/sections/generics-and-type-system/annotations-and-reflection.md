# Annotations y Reflection

Las annotations adjuntan metadata a declarations/type uses, mientras reflection inspecciona classes, methods, fields, constructors, generics y annotations en runtime. Los frameworks usan ambos para serialización, DI, testing y persistence.

```java
@Deprecated
public void oldApi() { }

Class<?> type = User.class;
for (var method : type.getDeclaredMethods()) {
    System.out.println(method.getName());
}
```

Reflection cambia seguridad de compile time y performance por flexibilidad. Prefiere llamadas tipadas cuando los tipos sean conocidos y cachea metadata repetida en infraestructura reflection-heavy.
