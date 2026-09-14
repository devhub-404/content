# Platform Types y Nullability Java

Cuando la nullability Java es incompleta, Kotlin usa platform types, permitiendo uso nullable o non-null con menos garantías. Las annotations Java modernas pueden mejorar el boundary, pero APIs legacy siguen siendo inciertas.

```kotlin
val value = javaApi.findName() // may be String! internally

val safe: String? = value
val required: String = requireNotNull(value)
```

Trata platform values como datos de boundary. Conviértelos a un tipo Kotlin nullable/non-null explícito y valida una vez.
