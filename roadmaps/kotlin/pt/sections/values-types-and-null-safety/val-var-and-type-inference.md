# `val`, `var` e Inferência de Tipo

`val` declara binding read-only e `var` binding reassignable. Kotlin infere tipos locais quando possível, mas o valor continua com um tipo estático. Binding read-only não torna o objeto profundamente imutável.

```kotlin
val name = "Mina"
var count = 0

count += 1
```

Prefira `val` por default e `var` quando estado realmente muda. Type annotations ajudam em boundaries públicos, collections vazias ou quando inference fica específica demais.
