# Local Functions e Recursão

Functions podem ser aninhadas para manter helpers locais e closures capturam state externo. `tailrec` pede ao compiler para otimizar recursão de cauda elegível em loop.

```kotlin
fun factorial(n: Int): Long {
    tailrec fun loop(value: Int, acc: Long): Long =
        if (value <= 1) acc else loop(value - 1, acc * value)

    return loop(n, 1)
}
```

Use recursão quando espelha o problema e depth é controlado. `tailrec` não serve a toda recursão, então traversals profundos podem exigir stack explícita.
