# Objects e Companion Objects

`object` cria singleton com tipo e instância única. Companion objects associam members singleton a uma class e podem conter factories, constants ou implementar interfaces. Object expressions criam objetos anônimos locais.

```kotlin
object IdGenerator {
    private var next = 0L
    fun nextId(): Long = ++next
}

class User {
    companion object {
        fun guest() = User()
    }
}
```

Estado singleton é global no runtime e pode complicar testes/concorrência. Prefira ownership explícito quando estado varia por aplicação e use object para helpers stateless ou singleton real.
