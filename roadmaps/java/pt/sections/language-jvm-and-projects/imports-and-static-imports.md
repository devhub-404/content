# Imports e Static Imports

Import torna um tipo ou static member disponível por nome curto na compilation unit. Imports não instalam nem carregam dependencies; apenas afetam resolução de nomes. Tipos de `java.lang` e do package atual não precisam import comum.

```java
import java.time.Instant;
import static java.util.Comparator.comparing;

Instant now = Instant.now();
```

Evite wildcard imports quando escondem origem dos nomes. Static imports ajudam em constants, assertions e APIs DSL pequenas, mas em excesso dificultam descobrir de onde vem o comportamento.
