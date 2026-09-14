# Imports y Static Imports

Un import hace disponible un tipo o static member mediante un nombre corto dentro de una compilation unit. No instala ni carga dependencies; solo afecta resolución de nombres. Los tipos de `java.lang` y del package actual no necesitan import normal.

```java
import java.time.Instant;
import static java.util.Comparator.comparing;

Instant now = Instant.now();
```

Evita wildcard imports cuando oculten el origen de los nombres. Los static imports ayudan con constants, assertions y pequeñas APIs tipo DSL, pero en exceso dificultan saber de dónde viene el comportamiento.
