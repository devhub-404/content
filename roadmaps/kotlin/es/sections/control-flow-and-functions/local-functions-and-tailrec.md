# Local Functions y Recursión

Las functions pueden anidarse para mantener helpers locales y las closures capturan estado externo. `tailrec` pide al compiler optimizar recursión de cola elegible como loop.

```kotlin
fun factorial(n: Int): Long {
    tailrec fun loop(value: Int, acc: Long): Long =
        if (value <= 1) acc else loop(value - 1, acc * value)

    return loop(n, 1)
}
```

Usa recursión cuando refleje el problema y la depth esté controlada. `tailrec` no sirve para toda recursión, así que traversals profundos pueden requerir una stack explícita.
