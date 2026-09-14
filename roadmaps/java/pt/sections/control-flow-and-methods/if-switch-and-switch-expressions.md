# `if`, `switch` e Switch Expressions

`if` trata branching Boolean geral, enquanto `switch` moderno pode ser statement ou expression que produz valor. Arrow labels evitam fall-through acidental e switch expressions precisam ser exaustivas.

```java
String label = switch (status) {
    case READY -> "ready";
    case FAILED -> "failed";
    case PENDING -> "pending";
};
```

Prefira switch expression para mapping fechado de uma entrada a um resultado. O switch clássico ainda serve a casos imperativos, mas fall-through deve ser deliberado.
