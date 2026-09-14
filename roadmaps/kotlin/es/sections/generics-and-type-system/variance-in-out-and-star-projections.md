# Varianza: `in`, `out` y Star Projections

Declaration-site variance permite declarar que un tipo solo produce (`out`) o consume (`in`) T, habilitando subtype relationships seguros. Las projections manejan casos donde variance no puede fijarse en la declaration.

```kotlin
interface Producer<out T> {
    fun produce(): T
}

interface Consumer<in T> {
    fun consume(value: T)
}
```

La varianza debe reflejar la API real. Un tipo que consume y produce T normalmente es invariant. No añadas `out` o `in` solo para que un assignment compile.
