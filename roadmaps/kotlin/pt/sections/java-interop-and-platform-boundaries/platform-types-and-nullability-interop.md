# Platform Types e Nullability Java

Quando Java nullability é incompleta, Kotlin usa platform types, permitindo uso nullable ou non-null com menos guarantees. Annotations Java modernas podem melhorar boundary, mas APIs legacy seguem incertas.

```kotlin
val value = javaApi.findName() // may be String! internally

val safe: String? = value
val required: String = requireNotNull(value)
```

Trate platform values como dados de boundary. Converta para tipo Kotlin nullable/non-null explícito e valide uma vez.
