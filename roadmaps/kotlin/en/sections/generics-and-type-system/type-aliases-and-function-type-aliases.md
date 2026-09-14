# Type Aliases

A type alias creates another source-level name for an existing type, including complex function or generic types. It improves readability but does not create a distinct runtime or compile-time type identity.

```kotlin
typealias UserId = String
typealias Handler = (Request) -> Response
```

Use a value class or wrapper when two values with the same representation must not be mixed. Use aliases when identity should remain the same and the goal is simply to give a verbose type a meaningful name.
