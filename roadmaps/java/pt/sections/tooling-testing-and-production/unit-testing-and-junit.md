# Unit Testing com JUnit

JUnit é o ecossistema de unit testing padrão de fato, integrado por build tools e IDEs. Tests podem usar lifecycle hooks, parameterized cases, tags, assertions e extensions.

```java
@Test
void add_sumsValues() {
    var calculator = new Calculator();
    assertEquals(5, calculator.add(2, 3));
}
```

Teste comportamento público e invariantes, não estrutura private. Use integration tests para banco, HTTP, files, serialization e framework config quando mocks não provam wiring real.
