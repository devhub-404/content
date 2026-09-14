# Value Classes e Enums

Value classes envolvem um valor em tipo distinto e frequentemente evitam wrapper allocation, úteis para IDs e units. Enums modelam conjunto fixo de constants com properties/methods.

```kotlin
@JvmInline
value class UserId(val value: String)

enum class Status { PENDING, READY, FAILED }
```

Use value class para type safety sem identidade de objeto, mas entenda que boxing ainda pode ocorrer. Use enum para constants simples e sealed hierarchy quando variants carregam dados diferentes.
