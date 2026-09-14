# Unit Testing with JUnit

JUnit is the de facto standard unit-testing ecosystem for Java, integrated by build tools and IDEs. Tests can use lifecycle hooks, parameterized cases, nested organization, tags, assertions, and extension mechanisms.

```java
@Test
void add_sumsValues() {
    var calculator = new Calculator();
    assertEquals(5, calculator.add(2, 3));
}
```

Test public behavior and invariants rather than private implementation structure. Use integration tests for databases, HTTP, files, serialization, and framework configuration where mocks cannot prove the real system wiring.
