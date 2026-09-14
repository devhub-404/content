# Variables, `final`, and `var`

Local-variable type inference with `var` asks the compiler to infer one static type from the initializer. `final` prevents a variable from being assigned another value after initialization, but a final reference can still point to a mutable object whose contents change.

```java
var name = "Mina";
final int maxRetries = 5;

name = name.toUpperCase();
```

Use `var` where the inferred type remains obvious and the initializer communicates enough context. Use explicit types at important boundaries or where inference hides a meaningful abstraction. `final` is useful for invariants and captured variables, but Java does not require every unchanged local to be declared final.
