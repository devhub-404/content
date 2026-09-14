# Imports and Static Imports

An import makes a type or static member available by a short name inside one compilation unit. Imports do not load libraries or add dependencies; they only affect compile-time name resolution. Types in `java.lang` and the current package are available without ordinary imports.

```java
import java.time.Instant;
import static java.util.Comparator.comparing;

Instant now = Instant.now();
```

Avoid wildcard imports in public examples and codebases where they make name origins ambiguous. Static imports are useful for well-known constants, assertions, or small DSL-like APIs, but excessive use can hide where behavior comes from.
