# Unit Testing con JUnit

JUnit es el ecosistema de unit testing de facto, integrado por build tools e IDEs. Los tests pueden usar lifecycle hooks, casos parametrizados, tags, assertions y extensions.

```java
@Test
void add_sumsValues() {
    var calculator = new Calculator();
    assertEquals(5, calculator.add(2, 3));
}
```

Prueba comportamiento público e invariantes, no estructura private. Usa integration tests para base de datos, HTTP, files, serialización y configuración de frameworks cuando los mocks no prueben el wiring real.
