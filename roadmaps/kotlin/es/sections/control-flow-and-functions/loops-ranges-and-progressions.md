# Loops, Ranges y Progressions

`for` itera valores compatibles con las conventions de iteration y `while`/`do-while` manejan repetición por condición. Ranges/progressions ofrecen secuencias concisas y `..<` usa límite superior exclusivo.

```kotlin
for (i in 0..<10) {
    println(i)
}

for (value in values) {
    println(value)
}
```

Prefiere iteración por elemento cuando el índice no importe. Usa `indices`, `withIndex` o ranges cuando la posición sea relevante.
