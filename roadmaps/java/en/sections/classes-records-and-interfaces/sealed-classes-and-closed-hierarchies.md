# Sealed Classes and Closed Hierarchies

A sealed class or interface restricts which types may extend or implement it. Permitted subclasses must explicitly continue as `final`, `sealed`, or `non-sealed`, giving the compiler and readers a controlled hierarchy.

```java
public sealed interface Result
    permits Success, Failure { }

record Success(String value) implements Result { }
record Failure(String message) implements Result { }
```

Sealed hierarchies are excellent for domain alternatives that should remain closed and work naturally with exhaustive pattern switches. Use open interfaces when third-party implementations are part of the intended extension model.
