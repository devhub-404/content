# Loops, Ranges e Progressions

`for` itera valores compatíveis com conventions de iteration, e `while`/`do-while` tratam repetição por condição. Ranges/progressions oferecem sequências concisas e `..<` usa limite superior exclusivo.

```kotlin
for (i in 0..<10) {
    println(i)
}

for (value in values) {
    println(value)
}
```

Prefira iteração por elemento quando índice não importa. Use `indices`, `withIndex` ou ranges quando posição é relevante.
